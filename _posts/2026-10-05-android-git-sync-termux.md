---
title:
tags:
date: 2026-10-05
toc: true
toc_sticky: true
---


# handygit — Project Documentation

  

Dense reference for the `2026-08-05-handygit` base folder. Covers purpose, layout,

environment, the sync mechanism, known failure modes, and recurring operations.

  

> ⚠️ **Secrets live in this folder.** `readme.md` (connection facts) and `.env` hold/held

> credentials. Never print the Termux SSH password or any PAT into chat, commits, or logs.

> Keep `.env` git-ignored. Revoke any PAT that was ever pasted into a workspace file.

  

---

  

## 1. Purpose

  

Keep an **Obsidian vault** that lives on an Android phone in sync with **GitHub**, using

**Termux** git on the phone and driving/diagnosing it from a **Windows PC over SSH** when

needed. The phone is low-RAM, so the Obsidian git plugin / MGit are unreliable for large

syncs; the Termux CLI path (and a one-tap widget script) is the reliable mechanism.

  

- Vault / repo on phone: `/storage/emulated/0/Documents/hacker-notes`

- GitHub remote: `https://github.com/softwareengel/hacker-notes.git` (branch `master`, HTTPS)

- Note content lives under `_posts/`, `_asset/`, `Excalidraw/` (Obsidian/Jekyll-style).

  

## 2. Folder layout

  

```

2026-08-05-handygit/

  .env                 # git-ignored; tokens/secrets (do not commit)

  CLAUDE.md            # LLM behavioral guidelines (think-first, simplicity, surgical edits)

  readme.md            # connection facts + exposed secrets (REDACTED); handy quick notes

  restore_block.md     # Termux reinstall/restore + optional SSH enable commands

  doc/

    documentation.md   # this file

    chatlog/

      readme.md                                   # "Dont Touch" — chatlog conventions

      2026-08-05-android-git-push-over-ssh.md     # initial setup + MGit/widget + F-Droid swap

      2026-09-14-fix-phone-git-sync-pat.md        # wiped-PAT (0-byte creds) incident

      2026-10-05-fix-phone-git-sync-divergence-and-harden-script.md  # divergence + script hardening

```

  

### Conventions (`doc/chatlog/readme.md`, do not touch)

- Full session chat logs go to `doc/chatlog/YYYY-MM-DD-TOPIC.md`.

- `doc/documentation.md` holds dense but full project information (this file).

  

## 3. Environment / connection facts

  

| Item | Value |

|------|-------|

| Phone Termux user | `u0_a505` |

| Phone LAN IP | `10.0.0.45` (same WiFi as PC) |

| Termux sshd port | `8022` |

| SSH from PC | `ssh -p 8022 u0_a505@10.0.0.45` |

| PC SSH client | built-in OpenSSH for Windows |

| Repo path (phone) | `/storage/emulated/0/Documents/hacker-notes` |

| Branch / remote | `master` → `github.com/softwareengel/hacker-notes` (HTTPS) |

| Credential helper | `git config --global credential.helper store` |

| Credential file | `~/.git-credentials` (mode 600, ~74 bytes when valid) |

| Sync script | `~/.shortcuts/sync-notes.sh` (+ `.bak` backup) |

| One-tap trigger | **Termux:Widget** (F-Droid build) → `~/.shortcuts/` |

  

**Android quirks**

- Android suspends Termux → SSH drops ("Connection reset"). Fix: `termux-wake-lock` then

  `sshd` after every Termux restart; connect with `-o ServerAliveInterval=20 -o ServerAliveCountMax=3`.

- Phone regenerates its SSH host key on reinstall → clear it on the PC:

  `ssh-keygen -R "[10.0.0.45]:8022"`.

- `ip addr` fails in Termux ("cannot bind netlink socket"); get IP from Wi-Fi settings or `ifconfig`.

- Termux:Widget needs **"Display over other apps"** permission to launch from a tap.

- `termux-wake-lock` may throw a harmless `InvocationTargetException`; sync still succeeds

  (silence with `termux-wake-lock 2>/dev/null || true`).

- Termux must be the **F-Droid** build (not Play Store) for Termux:Widget signature to match.

  

## 4. Sync mechanism — `~/.shortcuts/sync-notes.sh`

  

Tap-to-sync flow: wake-lock → stage all → commit if changes → pull (merge) → push → unlock.

  

```bash

#!/data/data/com.termux/files/usr/bin/bash

termux-wake-lock

cd /storage/emulated/0/Documents/hacker-notes || { echo "repo not found"; exit 1; }

echo "== syncing hacker-notes =="

git add -A

git diff --cached --quiet || git commit -m "notes sync $(date '+%Y-%m-%d %H:%M:%S')"

git pull --no-rebase --no-edit origin master || { echo "PULL FAILED (resolve conflict manually)"; termux-wake-unlock; exit 1; }

git push origin master || { echo "PUSH FAILED (check auth / PAT)"; termux-wake-unlock; exit 1; }

echo "== done =="

termux-wake-unlock

```

  

- `pull --no-rebase` creates a merge commit when local and remote have diverged.

- **Push failure detection** (added 2026-10-05): a failed push prints `PUSH FAILED`,

  releases the wake-lock, and exits non-zero instead of falsely printing `== done ==`.

- Previous version backed up at `~/.shortcuts/sync-notes.sh.bak`.

  

## 5. Known failure modes

  

### A) Push auth error — wiped PAT (0-byte credentials) — 2026-09-14

- **Symptom:** `git push` fails: *"Invalid username or token / password authentication is

  not supported."*

- **Cause:** `~/.git-credentials` is **0 bytes**. The `store` helper **erases** the stored

  entry after a push with an invalid/expired PAT.

- **Fix:** one interactive `git push origin master` — Username `softwareengel`, Password =

  **fresh classic PAT** (`repo` scope), typed directly in the terminal. `store` repopulates

  the file (~74 bytes).

- **Verify:** `wc -c ~/.git-credentials` (non-zero) and `git status -sb` = `## master...origin/master`.

  

### B) Divergence — not auth — 2026-10-05

- **Symptom:** "sync issue" but creds are healthy (~74 bytes) and `git fetch` works.

- **Cause:** phone has uncommitted notes **and** origin has newer `vault backup` commits →

  local `behind N` / diverged.

- **Fix:** just run `bash ~/.shortcuts/sync-notes.sh` (commit → pull --no-rebase merge →

  push). No PAT needed.

  

### Diagnose first (distinguishes A vs B)

```bash

wc -c ~/.git-credentials                                   # 0 bytes ⇒ case A (PAT)

git config --global --get credential.helper                # expect: store

git remote -v                                              # expect HTTPS hacker-notes

git fetch origin                                           # reachability

git status -sb                                             # ahead/behind

git log --oneline --left-right master...origin/master      # who has what commits

```

  

## 6. Recovery / fresh setup (`restore_block.md`)

  

Uninstalling Termux wipes its home (token, script, git/openssh) but **not** the vault

(shared storage). To restore:

  

```bash

pkg update && pkg upgrade -y

pkg install -y git openssh

termux-setup-storage

git config --global credential.helper store

git config --global --add safe.directory /storage/emulated/0/Documents/hacker-notes

printf 'https://softwareengel:YOUR_FRESH_PAT@github.com\n' > ~/.git-credentials

chmod 600 ~/.git-credentials

mkdir -p ~/.shortcuts

# recreate ~/.shortcuts/sync-notes.sh (see §4), then: chmod +x ~/.shortcuts/sync-notes.sh

```

  

Optional SSH access from the PC (run interactively — `passwd` prompts):

```bash

passwd            # set a login password

termux-wake-lock  # keep Termux alive

sshd              # start ssh server on 8022

```

Then on the PC: `ssh-keygen -R "[10.0.0.45]:8022"` before reconnecting.

  

## 7. History (chatlogs)

  

- **2026-08-05** — Initial fix: push failed (GitHub rejects password auth; PAT required).

  Pushed via one-shot token URL; committed untracked notes; set up `credential.helper store`;

  created `sync-notes.sh`; switched Termux to F-Droid for Termux:Widget; verified one-tap sync.

- **2026-09-14** — Case A recurrence: 0-byte `~/.git-credentials`; re-authenticated with a

  fresh PAT via one interactive push; verified clean.

- **2026-10-05** — Case B: divergence (healthy creds). Sync script reconciled and pushed.

  Hardened `sync-notes.sh` with push failure detection; backed up original.

  

## 8. Security checklist

  

- Revoke every PAT ever pasted into a workspace file (`readme.md`, `.env`); keep only the

  one currently stored on the phone.

- Keep `.env` git-ignored so tokens never land in the vault.

- Never route a PAT or the SSH password through chat — type them directly in the terminal.

- `~/.git-credentials` must be mode `600`.