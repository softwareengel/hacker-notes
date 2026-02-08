---
title: openclaw results
tags:
date: 2026-02-08
toc: true
toc_sticky: true
---

![](../_asset/2026-02-08-openclaw-results-1770568972110.webp)
# openclaw DIY 

![](../_asset/2026-02-08-openclaw-results-1770568960277.webp)


## Setup 
- like Nano bot - only start openclaw 


![](../_asset/2026-02-05-nanobot-results-1770329326699.webp)


## install Skripts 

``` bash

git clone https://github.com/openclaw/openclaw.git
sudo apt install npm
cd openclaw
sudo npm install -g pnpm
sudo apt install cmake
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
nvm install 22
nvm use 22

pnpm install
pnpm ui:build
pnpm build

pnpm openclaw onboard --install-daemon

pnpm gateway:watch

pnpm openclaw status  
cd /home/ve/src/github/openclaw && pnpm openclaw config set logging.level trace
pnpm openclaw gateway stop
pnpm openclaw gateway start
pnpm openclaw gateway --verbose --raw-stream --ws-log full

```


![](../_asset/2026-02-08-openclaw-results-1770569023967.webp)



## REsults 

![](../_asset/2026-02-08-openclaw-results-1770569903651.webp)

![](../_asset/2026-02-08-openclaw-results-1770569930831.webp)

![](../_asset/2026-02-08-openclaw-results-1770569949105.webp)

![](../_asset/2026-02-08-openclaw-results-1770569971850.webp)

![](../_asset/2026-02-08-openclaw-results-1770569991245.webp)

![](../_asset/2026-02-08-openclaw-results-1770570020846.webp)

![](../_asset/2026-02-08-openclaw-results-1770570033344.webp)


![](../_asset/2026-02-08-openclaw-results-1770570091418.webp)


![](../_asset/2026-02-08-openclaw-results-1770570133616.webp)


![](../_asset/2026-02-08-openclaw-results-1770570176001.webp)


![](../_asset/2026-02-08-openclaw-results-1770570187675.webp)

![](../_asset/2026-02-08-openclaw-results-1770581832827.webp)



![](../_asset/2026-02-08-openclaw-results-1770581849129.webp)

![](../_asset/2026-02-08-openclaw-results-1770581868578.webp)

![](../_asset/2026-02-08-openclaw-results-1770581889428.webp)

## web ui 
![](../_asset/2026-02-08-openclaw-results-1770579419650.webp)


![](../_asset/2026-02-08-openclaw-results-1770579477430.webp)

![](../_asset/2026-02-08-openclaw-results-1770579498637.webp)

![](../_asset/2026-02-08-openclaw-results-1770579515989.webp)

![](../_asset/2026-02-08-openclaw-results-1770579549386.webp)

![](../_asset/2026-02-08-openclaw-results-1770579580283.webp)


![](../_asset/2026-02-08-openclaw-results-1770579617816.webp)


![](../_asset/2026-02-08-openclaw-results-1770579643091.webp)


![](../_asset/2026-02-08-openclaw-results-1770579670550.webp)

![](../_asset/2026-02-08-openclaw-results-1770579774370.webp)







### openai costs 
![](../_asset/2026-02-08-openclaw-results-1770583939416.webp)



## Links

https://github.com/openclaw/openclaw


# Logs 

### npm build
```
ve@ubuntu24mini:~/src/github/openclaw$ pnpm build 

> openclaw@2026.2.6-3 build /home/ve/src/github/openclaw
> pnpm canvas:a2ui:bundle && tsdown && pnpm build:plugin-sdk:dts && node --import tsx scripts/write-plugin-sdk-entry-dts.ts && node --import tsx scripts/canvas-a2ui-copy.ts && node --import tsx scripts/copy-hook-metadata.ts && node --import tsx scripts/write-build-info.ts && node --import tsx scripts/write-cli-compat.ts


> openclaw@2026.2.6-3 canvas:a2ui:bundle /home/ve/src/github/openclaw
> bash scripts/bundle-a2ui.sh

A2UI bundle up to date; skipping.
ℹ tsdown v0.20.3 powered by rolldown v1.0.0-rc.3
ℹ config file: /home/ve/src/github/openclaw/tsdown.config.ts 
ℹ entry: src/index.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/plugin-sdk/index.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/entry.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/extensionAPI.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ Build start
ℹ Cleaning 310 files
ℹ Granting execute permission to dist/index.js
ℹ dist/plugin-sdk/index.js                        809.82 kB │ gzip: 176.79 kB
ℹ dist/plugin-sdk/pi-model-discovery-Dw3A6oXH.js    1.12 kB │ gzip:   0.52 kB
ℹ 2 files, total: 810.94 kB
ℹ dist/index.js                             235.53 kB │ gzip:  52.45 kB
ℹ dist/reply-WIhFad77.js                   2275.19 kB
ℹ dist/gateway-cli-DOw-e5er.js              642.29 kB │ gzip: 150.71 kB
ℹ dist/config-URF4ccgD.js                   177.19 kB │ gzip:  34.52 kB
ℹ dist/onboarding-BLYTLUXq.js               122.44 kB │ gzip:  31.73 kB
ℹ dist/manager-C_EmpJ9X.js                  118.74 kB │ gzip:  24.65 kB
ℹ dist/onboard-skills-BTuYj6Ns.js           117.39 kB │ gzip:  25.17 kB
ℹ dist/sandbox-Ru71h1Oo.js                  108.37 kB │ gzip:  24.24 kB
ℹ dist/model-selection-Dd2NmplP.js          100.83 kB │ gzip:  22.10 kB
ℹ dist/doctor-CAZhAY4C.js                    99.86 kB │ gzip:  25.41 kB
ℹ dist/models-cli-ofQUeVnv.js                98.07 kB │ gzip:  22.18 kB
ℹ dist/deliver-Ck-fH_m-.js                   84.54 kB │ gzip:  21.11 kB
ℹ dist/tui-BHVdiSgz.js                       84.07 kB │ gzip:  20.08 kB
ℹ dist/routes-DsnRe_Nf.js                    78.94 kB │ gzip:  15.60 kB
ℹ dist/audit-CsZB5GGI.js                     74.57 kB │ gzip:  18.25 kB
ℹ dist/client-fNmFILBZ.js                    67.04 kB │ gzip:  12.01 kB
ℹ dist/chrome-BNSd7Bie.js                    63.21 kB │ gzip:  16.15 kB
ℹ dist/channels-cli-DGvhNLbq.js              55.53 kB │ gzip:  14.03 kB
ℹ dist/pw-ai-DYpQO6HI.js                     54.80 kB │ gzip:  12.66 kB
ℹ dist/health-format-D5Gpg8bc.js             53.19 kB │ gzip:  12.93 kB
ℹ dist/nodes-cli-DV3K0TSJ.js                 51.83 kB │ gzip:  11.22 kB
ℹ dist/node-cli-CIULe485.js                  48.81 kB │ gzip:  12.35 kB
ℹ dist/pi-embedded-helpers-BMI-3k6W.js       44.89 kB │ gzip:  11.85 kB
ℹ dist/update-runner-D1hba9hW.js             42.52 kB │ gzip:   9.38 kB
ℹ dist/github-copilot-auth-CR5x7nk1.js       40.92 kB │ gzip:   7.88 kB
ℹ dist/update-cli-C_zBDCd1.js                38.86 kB │ gzip:  10.90 kB
ℹ dist/channel-summary-BoPV1G-Z.js           36.52 kB │ gzip:   8.49 kB
ℹ dist/hooks-cli-Be1eZvzO.js                 35.59 kB │ gzip:   8.17 kB
ℹ dist/configure-B5MRfx8R.js                 29.91 kB │ gzip:   7.83 kB
ℹ dist/daemon-cli-BZ4awAbA.js                29.83 kB │ gzip:   7.13 kB
ℹ dist/exec-approvals-DmzWB9Zy.js            29.48 kB │ gzip:   6.89 kB
ℹ dist/acp-cli-S1NA5jDG.js                   28.84 kB │ gzip:   7.87 kB
ℹ dist/agent-B2WI0qMu.js                     28.83 kB │ gzip:   7.22 kB
ℹ dist/subsystem-CAq3uyo7.js                 28.12 kB │ gzip:   8.09 kB
ℹ dist/server-context-vChIAqjH.js            27.81 kB │ gzip:   7.25 kB
ℹ dist/skills-D5JDj3TR.js                    26.80 kB │ gzip:   6.94 kB
ℹ dist/completion-cli-D2lcf0fe.js            26.79 kB │ gzip:   6.87 kB
ℹ dist/session-cost-usage-C5MMXOZi.js        25.33 kB │ gzip:   5.95 kB
ℹ dist/cron-cli-DWLXq-tD.js                  23.66 kB │ gzip:   5.86 kB
ℹ dist/service-BZesBIaG.js                   23.23 kB │ gzip:   5.57 kB
ℹ dist/onboard-channels-By5mh3L5.js          22.93 kB │ gzip:   5.86 kB
ℹ dist/image-CGUNQWBV.js                     22.26 kB │ gzip:   6.53 kB
ℹ dist/sandbox-cli-9vBqYBlK.js               21.88 kB │ gzip:   5.66 kB
ℹ dist/qmd-manager-DNvtC06N.js               20.81 kB │ gzip:   6.12 kB
ℹ dist/manifest-registry-DHaa1SJb.js         20.25 kB │ gzip:   5.07 kB
ℹ dist/service-audit-BYmA1hHd.js             18.65 kB │ gzip:   4.85 kB
ℹ dist/daemon-runtime-Kbd1PhO5.js            18.24 kB │ gzip:   5.12 kB
ℹ dist/plugins-BlF-ZPkH.js                   17.98 kB │ gzip:   3.96 kB
ℹ dist/plugin-auto-enable-DOednkDe.js        16.61 kB │ gzip:   4.31 kB
ℹ dist/tool-display-BxZG0o1b.js              16.39 kB │ gzip:   3.82 kB
ℹ dist/security-cli-CXGIqAhh.js              16.29 kB │ gzip:   4.67 kB
ℹ dist/plugins-cli-D7mnimLL.js               16.24 kB │ gzip:   4.47 kB
ℹ dist/login-qr-DGMCN3St.js                  16.17 kB │ gzip:   5.28 kB
ℹ dist/hooks-status-DepPyfBb.js              16.07 kB │ gzip:   4.24 kB
ℹ dist/gmail-setup-utils-QpN7TEXS.js         15.38 kB │ gzip:   4.47 kB
ℹ dist/webhooks-cli-D4wyKxFQ.js              14.57 kB │ gzip:   4.00 kB
ℹ dist/systemd-B-3NdMmA.js                   14.35 kB │ gzip:   4.14 kB
ℹ dist/installs-BhEjOqPy.js                  14.05 kB │ gzip:   3.50 kB
ℹ dist/exec-approvals-cli-CWSJ4YSY.js        14.05 kB │ gzip:   3.54 kB
ℹ dist/agent-scope-4nAkb5YL.js               13.38 kB │ gzip:   3.56 kB
ℹ dist/pairing-store-DwvRrpqV.js             11.95 kB │ gzip:   3.13 kB
ℹ dist/skills-cli-ClIV7qUO.js                11.94 kB │ gzip:   2.98 kB
ℹ dist/ws-log-DoIdOhb1.js                    11.83 kB │ gzip:   2.87 kB
ℹ dist/call-DoytZWzC.js                      11.01 kB │ gzip:   3.30 kB
ℹ dist/tailscale-BVGD9gSD.js                  9.01 kB │ gzip:   2.82 kB
ℹ dist/accounts-DkUtJa-O.js                   8.89 kB │ gzip:   2.60 kB
ℹ dist/pi-tools.policy-DdBp13AO.js            8.81 kB │ gzip:   2.44 kB
ℹ dist/update-DzMcwy1G.js                     8.71 kB │ gzip:   2.19 kB
ℹ dist/table-CLtGjVsx.js                      8.48 kB │ gzip:   2.76 kB
ℹ dist/logs-cli-CJoQqrRN.js                   8.33 kB │ gzip:   2.81 kB
ℹ dist/directory-cli-B8fqEnJ8.js              7.90 kB │ gzip:   1.92 kB
ℹ dist/server-node-events-B0DgTW--.js         7.80 kB │ gzip:   2.24 kB
ℹ dist/dns-cli-rINfsSWf.js                    7.79 kB │ gzip:   2.90 kB
ℹ dist/session-key-ezJ78bLC.js                7.68 kB │ gzip:   1.87 kB
ℹ dist/skill-scanner-BoGjHXUZ.js              7.68 kB │ gzip:   2.56 kB
ℹ dist/sqlite-BW8p11HW.js                     7.41 kB │ gzip:   2.49 kB
ℹ dist/skills-status-CEvVUD3U.js              7.29 kB │ gzip:   2.28 kB
ℹ dist/devices-cli-CDVjrGg3.js                7.27 kB │ gzip:   2.20 kB
ℹ dist/exec-HEWTMJ7j.js                       7.16 kB │ gzip:   2.39 kB
ℹ dist/utils-CKSrBNwq.js                      6.83 kB │ gzip:   2.56 kB
ℹ dist/paths-scjhy7N2.js                      6.83 kB │ gzip:   1.95 kB
ℹ dist/auth-CbhB03Rz.js                       6.35 kB │ gzip:   1.80 kB
ℹ dist/shared-BmtNKsPq.js                     5.69 kB │ gzip:   2.04 kB
ℹ dist/docs-cli-Bh1Coji2.js                   5.55 kB │ gzip:   2.02 kB
ℹ dist/pairing-cli-DiHDq_PT.js                5.19 kB │ gzip:   1.93 kB
ℹ dist/widearea-dns-D9Al4QRv.js               5.04 kB │ gzip:   1.93 kB
ℹ dist/nodes-screen-DT5HvhJV.js               4.96 kB │ gzip:   1.32 kB
ℹ dist/auth-health-6GAdWae9.js                4.94 kB │ gzip:   1.51 kB
ℹ dist/net-C8YRVt16.js                        4.39 kB │ gzip:   1.49 kB
ℹ dist/message-channel-Bpfe5l5f.js            4.30 kB │ gzip:   1.28 kB
ℹ dist/progress-xpLtQsNY.js                   4.16 kB │ gzip:   1.38 kB
ℹ dist/rpc-QakyFMzt.js                        4.12 kB │ gzip:   1.74 kB
ℹ dist/github-copilot-token-pGSmVaW-.js       3.97 kB │ gzip:   1.55 kB
ℹ dist/dispatcher-DqwvWXk8.js                 3.93 kB │ gzip:   1.58 kB
ℹ dist/system-cli-CnlB9-gO.js                 3.90 kB │ gzip:   1.19 kB
ℹ dist/redact-DJCFY628.js                     3.62 kB │ gzip:   1.43 kB
ℹ dist/shared-C8_5pNbb.js                     3.21 kB │ gzip:   1.16 kB
ℹ dist/systemd-linger-N-cIaegf.js             3.19 kB │ gzip:   1.01 kB
ℹ dist/cli-CKddHOE-.js                        3.09 kB │ gzip:   1.31 kB
ℹ dist/archive-Dy3Ezb-5.js                    3.00 kB │ gzip:   1.16 kB
ℹ dist/constants-HPrOsATF.js                  2.88 kB │ gzip:   0.79 kB
ℹ dist/path-env-DP3DsVge.js                   2.83 kB │ gzip:   1.11 kB
ℹ dist/tui-cli-DHWbCi4I.js                    2.81 kB │ gzip:   1.30 kB
ℹ dist/openclaw-root-Cvotktkd.js              2.80 kB │ gzip:   0.80 kB
ℹ dist/clack-prompter-CEKDd_Vg.js             2.61 kB │ gzip:   0.86 kB
ℹ dist/note-B5HnoeZX.js                       2.46 kB │ gzip:   0.91 kB
ℹ dist/control-service-DjUCiZsm.js            2.44 kB │ gzip:   0.95 kB
ℹ dist/paths-CR6bsrfc.js                      2.25 kB │ gzip:   0.73 kB
ℹ dist/channel-options-BUbn00Tq.js            2.24 kB │ gzip:   0.92 kB
ℹ dist/node-service-BAYHx0E7.js               2.09 kB │ gzip:   0.62 kB
ℹ dist/channel-selection-BPXp-Ft6.js          2.06 kB │ gzip:   0.73 kB
ℹ dist/command-format-ChfKqObn.js             1.95 kB │ gzip:   0.74 kB
ℹ dist/brew-CAcErcKz.js                       1.65 kB │ gzip:   0.58 kB
ℹ dist/usage-format-DvowRSs-.js               1.50 kB │ gzip:   0.58 kB
ℹ dist/format-B7OjpGnt.js                     1.28 kB │ gzip:   0.61 kB
ℹ dist/parse-log-line-CARp5QyJ.js             1.23 kB │ gzip:   0.52 kB
ℹ dist/env-0_mKbEWW.js                        1.21 kB │ gzip:   0.58 kB
ℹ dist/tailnet-DLDGNuH2.js                    1.21 kB │ gzip:   0.55 kB
ℹ dist/gateway-rpc-CFy1WFmn.js                1.17 kB │ gzip:   0.62 kB
ℹ dist/systemd-hints-DO88c_nD.js              1.11 kB │ gzip:   0.55 kB
ℹ dist/is-main-B6kCyqsv.js                    1.00 kB │ gzip:   0.40 kB
ℹ dist/cli-utils-BkRQdAoC.js                  0.98 kB │ gzip:   0.47 kB
ℹ dist/status-D5UKnMVc.js                     0.97 kB │ gzip:   0.44 kB
ℹ dist/boolean-BgXe2hyu.js                    0.86 kB │ gzip:   0.38 kB
ℹ dist/pi-model-discovery-CV2V1HHz.js         0.84 kB │ gzip:   0.37 kB
ℹ dist/status-tCu4RWZH.js                     0.82 kB │ gzip:   0.35 kB
ℹ dist/deps-DnKN09y7.js                       0.81 kB │ gzip:   0.32 kB
ℹ dist/helpers-5yebzF4C.js                    0.79 kB │ gzip:   0.39 kB
ℹ dist/parse-BZz5lHzQ.js                      0.70 kB │ gzip:   0.36 kB
ℹ dist/help-format-Bozi4K9H.js                0.67 kB │ gzip:   0.30 kB
ℹ dist/transcript-events-ChU6IQwp.js          0.59 kB │ gzip:   0.29 kB
ℹ dist/channels-status-issues-CkX23PyE.js     0.55 kB │ gzip:   0.30 kB
ℹ dist/logging-TXWhN8jG.js                    0.50 kB │ gzip:   0.30 kB
ℹ dist/links-B5pRdmo1.js                      0.49 kB │ gzip:   0.31 kB
ℹ dist/ws-CEcdsnN9.js                         0.47 kB │ gzip:   0.24 kB
ℹ dist/parse-timeout-Du-wHHNi.js              0.46 kB │ gzip:   0.26 kB
ℹ dist/prompt-style-vzh0MGHs.js               0.45 kB │ gzip:   0.25 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js           0.42 kB │ gzip:   0.28 kB
ℹ dist/helpers-CSZtxHTa.js                    0.41 kB │ gzip:   0.26 kB
ℹ dist/pairing-labels-CCiIuKc3.js             0.26 kB │ gzip:   0.18 kB
ℹ dist/prompts-FbZThK8w.js                    0.24 kB │ gzip:   0.17 kB
ℹ dist/logging-BWRYHvLp.js                    0.01 kB │ gzip:   0.03 kB
ℹ 142 files, total: 6043.17 kB
[PLUGIN_TIMINGS] Warning: Your build spent significant time in plugin `tsdown:external`. See https://rolldown.rs/options/checks#plugintimings for more details.

✔ Build complete in 4085ms
✔ Build complete in 4087ms
ℹ Granting execute permission to dist/entry.js
ℹ dist/extensionAPI.js                   2378.70 kB
ℹ dist/pi-embedded-helpers-Cys_WnsE.js    299.64 kB │ gzip: 66.34 kB
ℹ dist/config-D2MHAhmn.js                 199.70 kB │ gzip: 39.73 kB
ℹ dist/manager-BU81i3n7.js                118.66 kB │ gzip: 24.64 kB
ℹ dist/model-selection-B_WLq45x.js         91.51 kB │ gzip: 20.39 kB
ℹ dist/deliver-FdxL6NZx.js                 83.15 kB │ gzip: 20.83 kB
ℹ dist/chrome-B3IuUad-.js                  62.08 kB │ gzip: 15.75 kB
ℹ dist/pw-ai-tNPuRNn3.js                   54.74 kB │ gzip: 12.63 kB
ℹ dist/image-DfA1WRrQ.js                   38.52 kB │ gzip: 10.07 kB
ℹ dist/exec-BMnoMcZW.js                    35.83 kB │ gzip: 10.59 kB
ℹ dist/agent-scope-BHIT6LIU.js             22.67 kB │ gzip:  5.41 kB
ℹ dist/qmd-manager-DFlNmQRv.js             20.70 kB │ gzip:  6.08 kB
ℹ dist/login-qr-BKQv-osk.js                16.05 kB │ gzip:  5.23 kB
ℹ dist/sqlite-D1XZ7Oej.js                   7.41 kB │ gzip:  2.49 kB
ℹ dist/paths-B1kfl4h5.js                    6.06 kB │ gzip:  1.73 kB
ℹ dist/github-copilot-token-B3SA95yo.js     3.97 kB │ gzip:  1.55 kB
ℹ dist/redact-BIMJ3ntQ.js                   3.51 kB │ gzip:  1.40 kB
ℹ dist/paths-O8Bl3giv.js                    2.06 kB │ gzip:  0.72 kB
ℹ dist/command-format-CFzL448l.js           1.93 kB │ gzip:  0.74 kB
ℹ dist/pi-model-discovery-EhM2JAQo.js       0.84 kB │ gzip:  0.37 kB
ℹ dist/transcript-events-JLH5W4He.js        0.59 kB │ gzip:  0.29 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js         0.42 kB │ gzip:  0.28 kB
ℹ 22 files, total: 3448.75 kB
[PLUGIN_TIMINGS] Warning: Your build spent significant time in plugin `tsdown:external`. See https://rolldown.rs/options/checks#plugintimings for more details.

✔ Build complete in 4417ms
ℹ dist/entry.js                              44.79 kB │ gzip:  12.54 kB
ℹ dist/loader-BsYrSp91.js                  2275.04 kB
ℹ dist/gateway-cli-BsiUicCD.js              642.24 kB │ gzip: 150.66 kB
ℹ dist/config-guard-BI-i6Hew.js             227.35 kB │ gzip:  49.42 kB
ℹ dist/config-CVC-02lU.js                   177.14 kB │ gzip:  34.51 kB
ℹ dist/status-C3GkF5iX.js                   119.38 kB │ gzip:  30.79 kB
ℹ dist/manager-BdvAC5a3.js                  118.65 kB │ gzip:  24.62 kB
ℹ dist/onboard-skills-Cjzuu1Aa.js           117.38 kB │ gzip:  25.25 kB
ℹ dist/sandbox-Bx4fVzog.js                  108.29 kB │ gzip:  24.08 kB
ℹ dist/auth-profiles-0bUrpTY2.js            100.74 kB │ gzip:  22.41 kB
ℹ dist/doctor-BprL2ieD.js                    99.75 kB │ gzip:  25.38 kB
ℹ dist/models-cli-CDyjRxY-.js                97.95 kB │ gzip:  22.10 kB
ℹ dist/deliver-BIDW_mg2.js                   84.53 kB │ gzip:  21.11 kB
ℹ dist/tui-uQnn3Xv0.js                       84.02 kB │ gzip:  20.05 kB
ℹ dist/routes-CL5x6Rpf.js                    78.93 kB │ gzip:  15.64 kB
ℹ dist/audit-CmS9aWEu.js                     74.55 kB │ gzip:  18.24 kB
ℹ dist/client-DUpe9pFX.js                    67.03 kB │ gzip:  12.00 kB
ℹ dist/errors-CZ9opC6L.js                    62.00 kB │ gzip:  15.75 kB
ℹ dist/channels-cli-DP18SWYt.js              55.46 kB │ gzip:  14.00 kB
ℹ dist/pw-ai-B7Fvw8DW.js                     54.74 kB │ gzip:  12.64 kB
ℹ dist/health-format-UG0Hrn1r.js             53.14 kB │ gzip:  12.91 kB
ℹ dist/nodes-cli-CzG7n4Ms.js                 51.73 kB │ gzip:  11.18 kB
ℹ dist/node-cli-Dgo-IYAQ.js                  48.70 kB │ gzip:  12.30 kB
ℹ dist/pi-embedded-helpers-U7qcMWTo.js       44.88 kB │ gzip:  11.80 kB
ℹ dist/update-runner-0hp30-vw.js             42.52 kB │ gzip:   9.39 kB
ℹ dist/github-copilot-auth-rIlU5brF.js       40.90 kB │ gzip:   7.87 kB
ℹ dist/update-cli-YMXrxbB4.js                38.79 kB │ gzip:  10.86 kB
ℹ dist/channel-summary-Cq07O8sV.js           36.51 kB │ gzip:   8.48 kB
ℹ dist/hooks-cli-DfNxtINP.js                 35.47 kB │ gzip:   8.12 kB
ℹ dist/configure-ok3Q8yxN.js                 29.85 kB │ gzip:   7.80 kB
ℹ dist/daemon-cli-DgLgnQaa.js                29.78 kB │ gzip:   7.11 kB
ℹ dist/exec-approvals-C-Dx43cR.js            29.48 kB │ gzip:   6.88 kB
ℹ dist/agent-fr7ENtJS.js                     28.82 kB │ gzip:   7.22 kB
ℹ dist/acp-cli-BA2r_kBp.js                   28.73 kB │ gzip:   7.82 kB
ℹ dist/server-context-yKyxyxOJ.js            27.80 kB │ gzip:   7.23 kB
ℹ dist/skills-CmU0Q92f.js                    26.75 kB │ gzip:   6.92 kB
ℹ dist/session-cost-usage-C9bgCj2T.js        25.33 kB │ gzip:   5.95 kB
ℹ dist/cron-cli-Bl_QPfcv.js                  23.56 kB │ gzip:   5.81 kB
ℹ dist/service-_JwSmGSn.js                   23.22 kB │ gzip:   5.55 kB
ℹ dist/onboard-channels-CE22BvSH.js          22.92 kB │ gzip:   5.85 kB
ℹ dist/image-Cx2j94Pk.js                     22.26 kB │ gzip:   6.53 kB
ℹ dist/sandbox-cli-CoDOlOGm.js               21.77 kB │ gzip:   5.62 kB
ℹ dist/qmd-manager-Cbv0THO_.js               20.76 kB │ gzip:   6.10 kB
ℹ dist/manifest-registry-C69Z-I4v.js         20.25 kB │ gzip:   5.07 kB
ℹ dist/service-audit-YyUL5jv1.js             18.65 kB │ gzip:   4.85 kB
ℹ dist/daemon-runtime-CR1S2Y0h.js            18.23 kB │ gzip:   5.09 kB
ℹ dist/plugins-DmOwDqqs.js                   17.93 kB │ gzip:   3.93 kB
ℹ dist/completion-cli-6G_Ii8fY.js            16.66 kB │ gzip:   4.44 kB
ℹ dist/plugin-auto-enable-BEhskCaY.js        16.60 kB │ gzip:   4.30 kB
ℹ dist/tool-display-DmgKs6-V.js              16.39 kB │ gzip:   3.82 kB
ℹ dist/security-cli-CqZ7UaSJ.js              16.17 kB │ gzip:   4.62 kB
ℹ dist/login-qr-DfKzWyRC.js                  16.16 kB │ gzip:   5.27 kB
ℹ dist/plugins-cli-DXwLQnj2.js               16.13 kB │ gzip:   4.42 kB
ℹ dist/hooks-status-CKmUPU-M.js              16.06 kB │ gzip:   4.24 kB
ℹ dist/gmail-setup-utils-Bi6W14MK.js         15.37 kB │ gzip:   4.47 kB
ℹ dist/webhooks-cli-BOlDRyNF.js              14.46 kB │ gzip:   3.95 kB
ℹ dist/systemd-8sIc6isV.js                   14.34 kB │ gzip:   4.12 kB
ℹ dist/installs-DsJkyWfL.js                  14.05 kB │ gzip:   3.50 kB
ℹ dist/exec-approvals-cli-CPeMbvxo.js        13.95 kB │ gzip:   3.50 kB
ℹ dist/agent-scope-xzSh3IZK.js               13.37 kB │ gzip:   3.56 kB
ℹ dist/pairing-store-CDcJ_3K0.js             11.94 kB │ gzip:   3.12 kB
ℹ dist/skills-cli-MAAySMBs.js                11.83 kB │ gzip:   2.93 kB
ℹ dist/ws-log-CPCss-ho.js                    11.82 kB │ gzip:   2.86 kB
ℹ dist/call-DTjuQHyM.js                      11.00 kB │ gzip:   3.30 kB
ℹ dist/register.subclis-DsVgdVQy.js          10.61 kB │ gzip:   2.89 kB
ℹ dist/accounts-MJ4mYpJN.js                   8.84 kB │ gzip:   2.57 kB
ℹ dist/commands-BFN6JELk.js                   8.81 kB │ gzip:   2.43 kB
ℹ dist/update-DNAVcIQ7.js                     8.71 kB │ gzip:   2.20 kB
ℹ dist/table-CJSx0YID.js                      8.47 kB │ gzip:   2.75 kB
ℹ dist/logs-cli-DXq1eZ2S.js                   8.22 kB │ gzip:   2.77 kB
ℹ dist/program-g8XIN3Vo.js                    8.14 kB │ gzip:   3.25 kB
ℹ dist/tailscale-9MusRvOi.js                  8.09 kB │ gzip:   2.48 kB
ℹ dist/directory-cli-C7ukwOrM.js              7.79 kB │ gzip:   1.87 kB
ℹ dist/server-node-events-BlVsV8zt.js         7.68 kB │ gzip:   2.20 kB
ℹ dist/dns-cli-BsOSvdTb.js                    7.68 kB │ gzip:   2.85 kB
ℹ dist/session-key-Dk6vSAOv.js                7.68 kB │ gzip:   1.87 kB
ℹ dist/skill-scanner-Bp1D9gra.js              7.68 kB │ gzip:   2.56 kB
ℹ dist/skills-status-DtXrj3fy.js              7.28 kB │ gzip:   2.27 kB
ℹ dist/run-main-Cv3jOztA.js                   7.25 kB │ gzip:   2.83 kB
ℹ dist/devices-cli-CwKNgw-1.js                7.17 kB │ gzip:   2.15 kB
ℹ dist/exec-B8JKbXKW.js                       7.15 kB │ gzip:   2.38 kB
ℹ dist/sqlite-DODNHWJb.js                     6.67 kB │ gzip:   2.25 kB
ℹ dist/utils-DX85MiPR.js                      6.65 kB │ gzip:   2.47 kB
ℹ dist/auth-DksjO6WG.js                       6.35 kB │ gzip:   1.80 kB
ℹ dist/shared-fnGLWyZ6.js                     5.68 kB │ gzip:   2.03 kB
ℹ dist/docs-cli-BH9bMx3a.js                   5.47 kB │ gzip:   1.98 kB
ℹ dist/pairing-cli-EZUIp4a-.js                5.09 kB │ gzip:   1.88 kB
ℹ dist/widearea-dns-CsSylzXH.js               5.04 kB │ gzip:   1.93 kB
ℹ dist/nodes-screen-DGlNPbk4.js               4.96 kB │ gzip:   1.32 kB
ℹ dist/auth-health-8T7CI5Io.js                4.93 kB │ gzip:   1.50 kB
ℹ dist/net-CWMMy37F.js                        4.39 kB │ gzip:   1.49 kB
ℹ dist/message-channel-BlgPSDAh.js            4.29 kB │ gzip:   1.27 kB
ℹ dist/progress-Da1ehW-x.js                   4.14 kB │ gzip:   1.37 kB
ℹ dist/rpc-C6o61iEs.js                        4.12 kB │ gzip:   1.74 kB
ℹ dist/github-copilot-token-SLWintYd.js       3.96 kB │ gzip:   1.54 kB
ℹ dist/wsl-B6yuTs1k.js                        3.93 kB │ gzip:   1.59 kB
ℹ dist/system-cli-De3tIflY.js                 3.79 kB │ gzip:   1.15 kB
ℹ dist/redact-B8YiFlwn.js                     3.62 kB │ gzip:   1.43 kB
ℹ dist/shared-C1XLEyB0.js                     3.20 kB │ gzip:   1.15 kB
ℹ dist/systemd-linger-SsSOsJST.js             3.19 kB │ gzip:   1.01 kB
ℹ dist/ports-0V-Mu4ch.js                      3.14 kB │ gzip:   1.12 kB
ℹ dist/archive-D0z3LZDK.js                    3.00 kB │ gzip:   1.16 kB
ℹ dist/cli-B4c4E5Cx.js                        2.97 kB │ gzip:   1.27 kB
ℹ dist/constants-D1op9uGI.js                  2.88 kB │ gzip:   0.79 kB
ℹ dist/path-env-h3xp5PqO.js                   2.83 kB │ gzip:   1.10 kB
ℹ dist/openclaw-root-9ILYSmJ9.js              2.80 kB │ gzip:   0.80 kB
ℹ dist/tui-cli-BMrYkt2x.js                    2.71 kB │ gzip:   1.26 kB
ℹ dist/clack-prompter-DuBVnTKy.js             2.60 kB │ gzip:   0.84 kB
ℹ dist/note-Ci08TSbV.js                       2.45 kB │ gzip:   0.90 kB
ℹ dist/control-service-tmird1Ap.js            2.42 kB │ gzip:   0.95 kB
ℹ dist/paths-BhxDUiio.js                      2.24 kB │ gzip:   0.72 kB
ℹ dist/node-service-Lc1LlnFH.js               2.09 kB │ gzip:   0.62 kB
ℹ dist/channel-selection-ucXSmjx7.js          2.06 kB │ gzip:   0.73 kB
ℹ dist/brew-CcZV0dSS.js                       1.65 kB │ gzip:   0.58 kB
ℹ dist/command-format-ayFsmwwz.js             1.58 kB │ gzip:   0.64 kB
ℹ dist/usage-format-E3bMcUMV.js               1.50 kB │ gzip:   0.58 kB
ℹ dist/format-CS7EI0xF.js                     1.28 kB │ gzip:   0.61 kB
ℹ dist/parse-log-line-C6szvNBZ.js             1.23 kB │ gzip:   0.52 kB
ℹ dist/tailnet-Byp3obcc.js                    1.21 kB │ gzip:   0.55 kB
ℹ dist/channel-options-DBFI1YRp.js            1.18 kB │ gzip:   0.56 kB
ℹ dist/gateway-rpc-D5MgIMVs.js                1.17 kB │ gzip:   0.62 kB
ℹ dist/command-options-rFZ_7aaM.js            1.13 kB │ gzip:   0.51 kB
ℹ dist/systemd-hints-Wim4Bq6j.js              1.11 kB │ gzip:   0.55 kB
ℹ dist/is-main-qJ675wPV.js                    1.00 kB │ gzip:   0.40 kB
ℹ dist/cli-utils-ByANh4Sp.js                  0.98 kB │ gzip:   0.47 kB
ℹ dist/status-CuggagUC.js                     0.96 kB │ gzip:   0.43 kB
ℹ dist/pi-model-discovery-DzEIEgHL.js         0.84 kB │ gzip:   0.37 kB
ℹ dist/status-CRIEi8Mc.js                     0.82 kB │ gzip:   0.35 kB
ℹ dist/deps-DWlrptVs.js                       0.81 kB │ gzip:   0.31 kB
ℹ dist/helpers-EKm3X92T.js                    0.79 kB │ gzip:   0.39 kB
ℹ dist/parse-gTOGQPH6.js                      0.70 kB │ gzip:   0.36 kB
ℹ dist/help-format-CfZ94KRN.js                0.66 kB │ gzip:   0.28 kB
ℹ dist/transcript-events-CZ8CG4ht.js          0.59 kB │ gzip:   0.29 kB
ℹ dist/channels-status-issues-NwwdCTbZ.js     0.55 kB │ gzip:   0.30 kB
ℹ dist/links-D0uzJbi6.js                      0.49 kB │ gzip:   0.31 kB
ℹ dist/logging-Cc7m6PTv.js                    0.49 kB │ gzip:   0.29 kB
ℹ dist/ws-D091yo4M.js                         0.47 kB │ gzip:   0.24 kB
ℹ dist/parse-timeout-CbVKLZ4B.js              0.46 kB │ gzip:   0.26 kB
ℹ dist/prompt-style-Dc0C5HC9.js               0.44 kB │ gzip:   0.23 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js           0.42 kB │ gzip:   0.28 kB
ℹ dist/helpers-CeoEYUfW.js                    0.41 kB │ gzip:   0.26 kB
ℹ dist/pairing-labels-bw3QFLZ0.js             0.26 kB │ gzip:   0.19 kB
ℹ dist/prompts-CXLLIBwP.js                    0.24 kB │ gzip:   0.17 kB
ℹ dist/logging-CfEk_PnX.js                    0.01 kB │ gzip:   0.03 kB
ℹ 144 files, total: 6051.28 kB
✔ Build complete in 4429ms

> openclaw@2026.2.6-3 build:plugin-sdk:dts /home/ve/src/github/openclaw
> tsc -p tsconfig.plugin-sdk.dts.json

[copy-hook-metadata] Copied boot-md/HOOK.md
[copy-hook-metadata] Copied command-logger/HOOK.md
[copy-hook-metadata] Copied session-memory/HOOK.md
[copy-hook-metadata] Copied soul-evil/HOOK.md
[copy-hook-metadata] Done

```

### pnpm openclaw status 

```
ve@ubuntu24mini:~/src/github/openclaw$ pnpm openclaw status  

> openclaw@2026.2.6-3 openclaw /home/ve/src/github/openclaw
> node scripts/run-node.mjs status

[openclaw] Building TypeScript (dist is stale).
ℹ tsdown v0.20.3 powered by rolldown v1.0.0-rc.3
ℹ config file: /home/ve/src/github/openclaw/tsdown.config.ts 
ℹ entry: src/index.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/plugin-sdk/index.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/extensionAPI.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ entry: src/entry.ts
ℹ target: node22.12.0
ℹ tsconfig: tsconfig.json
ℹ Build start
ℹ Granting execute permission to dist/index.js
ℹ dist/extensionAPI.js                   2378.72 kB
ℹ dist/pi-embedded-helpers-6EeO7S6D.js    299.64 kB │ gzip: 66.34 kB
ℹ dist/config-D2MHAhmn.js                 199.70 kB │ gzip: 39.73 kB
ℹ dist/manager-BU81i3n7.js                118.66 kB │ gzip: 24.64 kB
ℹ dist/model-selection-B_WLq45x.js         91.51 kB │ gzip: 20.39 kB
ℹ dist/deliver-BVFUvdgV.js                 83.15 kB │ gzip: 20.83 kB
ℹ dist/chrome-xcNOQZOI.js                  62.07 kB │ gzip: 15.74 kB
ℹ dist/pw-ai-CnBU8OzW.js                   54.74 kB │ gzip: 12.63 kB
ℹ dist/image-9syNWQPu.js                   38.52 kB │ gzip: 10.07 kB
ℹ dist/exec-BMnoMcZW.js                    35.83 kB │ gzip: 10.59 kB
ℹ dist/agent-scope-BHIT6LIU.js             22.67 kB │ gzip:  5.41 kB
ℹ dist/qmd-manager-DFlNmQRv.js             20.70 kB │ gzip:  6.08 kB
ℹ dist/login-qr-BKQv-osk.js                16.05 kB │ gzip:  5.23 kB
ℹ dist/sqlite-D1XZ7Oej.js                   7.41 kB │ gzip:  2.49 kB
ℹ dist/paths-B1kfl4h5.js                    6.06 kB │ gzip:  1.73 kB
ℹ dist/github-copilot-token-B3SA95yo.js     3.97 kB │ gzip:  1.55 kB
ℹ dist/redact-BIMJ3ntQ.js                   3.51 kB │ gzip:  1.40 kB
ℹ dist/paths-O8Bl3giv.js                    2.06 kB │ gzip:  0.72 kB
ℹ dist/command-format-CFzL448l.js           1.93 kB │ gzip:  0.74 kB
ℹ dist/pi-model-discovery-EhM2JAQo.js       0.84 kB │ gzip:  0.37 kB
ℹ dist/transcript-events-JLH5W4He.js        0.59 kB │ gzip:  0.29 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js         0.42 kB │ gzip:  0.28 kB
ℹ 22 files, total: 3448.75 kB
[PLUGIN_TIMINGS] Warning: Your build spent significant time in plugin `tsdown:external`. See https://rolldown.rs/options/checks#plugintimings for more details.

✔ Build complete in 3274ms
ℹ Granting execute permission to dist/entry.js
ℹ dist/plugin-sdk/index.js                        809.82 kB │ gzip: 176.78 kB
ℹ dist/plugin-sdk/pi-model-discovery-Dw3A6oXH.js    1.12 kB │ gzip:   0.52 kB
ℹ 2 files, total: 810.95 kB
✔ Build complete in 3598ms
ℹ dist/index.js                             235.53 kB │ gzip:  52.45 kB
ℹ dist/reply-WIhFad77.js                   2275.19 kB
ℹ dist/gateway-cli-DOw-e5er.js              642.29 kB │ gzip: 150.71 kB
ℹ dist/config-URF4ccgD.js                   177.19 kB │ gzip:  34.52 kB
ℹ dist/onboarding-BLYTLUXq.js               122.44 kB │ gzip:  31.73 kB
ℹ dist/manager-C_EmpJ9X.js                  118.74 kB │ gzip:  24.65 kB
ℹ dist/onboard-skills-BTuYj6Ns.js           117.39 kB │ gzip:  25.17 kB
ℹ dist/sandbox-Ru71h1Oo.js                  108.37 kB │ gzip:  24.24 kB
ℹ dist/model-selection-Dd2NmplP.js          100.83 kB │ gzip:  22.10 kB
ℹ dist/doctor-CAZhAY4C.js                    99.86 kB │ gzip:  25.41 kB
ℹ dist/models-cli-ofQUeVnv.js                98.07 kB │ gzip:  22.18 kB
ℹ dist/deliver-Ck-fH_m-.js                   84.54 kB │ gzip:  21.11 kB
ℹ dist/tui-BHVdiSgz.js                       84.07 kB │ gzip:  20.08 kB
ℹ dist/routes-DsnRe_Nf.js                    78.94 kB │ gzip:  15.60 kB
ℹ dist/audit-CsZB5GGI.js                     74.57 kB │ gzip:  18.25 kB
ℹ dist/client-fNmFILBZ.js                    67.04 kB │ gzip:  12.01 kB
ℹ dist/chrome-BNSd7Bie.js                    63.21 kB │ gzip:  16.15 kB
ℹ dist/channels-cli-DGvhNLbq.js              55.53 kB │ gzip:  14.03 kB
ℹ dist/pw-ai-DYpQO6HI.js                     54.80 kB │ gzip:  12.66 kB
ℹ dist/health-format-D5Gpg8bc.js             53.19 kB │ gzip:  12.93 kB
ℹ dist/nodes-cli-DV3K0TSJ.js                 51.83 kB │ gzip:  11.22 kB
ℹ dist/node-cli-CIULe485.js                  48.81 kB │ gzip:  12.35 kB
ℹ dist/pi-embedded-helpers-BMI-3k6W.js       44.89 kB │ gzip:  11.85 kB
ℹ dist/update-runner-D1hba9hW.js             42.52 kB │ gzip:   9.38 kB
ℹ dist/github-copilot-auth-CR5x7nk1.js       40.92 kB │ gzip:   7.88 kB
ℹ dist/update-cli-C_zBDCd1.js                38.86 kB │ gzip:  10.90 kB
ℹ dist/channel-summary-BoPV1G-Z.js           36.52 kB │ gzip:   8.49 kB
ℹ dist/hooks-cli-Be1eZvzO.js                 35.59 kB │ gzip:   8.17 kB
ℹ dist/configure-B5MRfx8R.js                 29.91 kB │ gzip:   7.83 kB
ℹ dist/daemon-cli-BZ4awAbA.js                29.83 kB │ gzip:   7.13 kB
ℹ dist/exec-approvals-DmzWB9Zy.js            29.48 kB │ gzip:   6.89 kB
ℹ dist/acp-cli-S1NA5jDG.js                   28.84 kB │ gzip:   7.87 kB
ℹ dist/agent-B2WI0qMu.js                     28.83 kB │ gzip:   7.22 kB
ℹ dist/subsystem-CAq3uyo7.js                 28.12 kB │ gzip:   8.09 kB
ℹ dist/server-context-vChIAqjH.js            27.81 kB │ gzip:   7.25 kB
ℹ dist/skills-D5JDj3TR.js                    26.80 kB │ gzip:   6.94 kB
ℹ dist/completion-cli-D2lcf0fe.js            26.79 kB │ gzip:   6.87 kB
ℹ dist/session-cost-usage-C5MMXOZi.js        25.33 kB │ gzip:   5.95 kB
ℹ dist/cron-cli-DWLXq-tD.js                  23.66 kB │ gzip:   5.86 kB
ℹ dist/service-BZesBIaG.js                   23.23 kB │ gzip:   5.57 kB
ℹ dist/onboard-channels-By5mh3L5.js          22.93 kB │ gzip:   5.86 kB
ℹ dist/image-CGUNQWBV.js                     22.26 kB │ gzip:   6.53 kB
ℹ dist/sandbox-cli-9vBqYBlK.js               21.88 kB │ gzip:   5.66 kB
ℹ dist/qmd-manager-DNvtC06N.js               20.81 kB │ gzip:   6.12 kB
ℹ dist/manifest-registry-DHaa1SJb.js         20.25 kB │ gzip:   5.07 kB
ℹ dist/service-audit-BYmA1hHd.js             18.65 kB │ gzip:   4.85 kB
ℹ dist/daemon-runtime-Kbd1PhO5.js            18.24 kB │ gzip:   5.12 kB
ℹ dist/plugins-BlF-ZPkH.js                   17.98 kB │ gzip:   3.96 kB
ℹ dist/plugin-auto-enable-DOednkDe.js        16.61 kB │ gzip:   4.31 kB
ℹ dist/tool-display-BxZG0o1b.js              16.39 kB │ gzip:   3.82 kB
ℹ dist/security-cli-CXGIqAhh.js              16.29 kB │ gzip:   4.67 kB
ℹ dist/plugins-cli-D7mnimLL.js               16.24 kB │ gzip:   4.47 kB
ℹ dist/login-qr-DGMCN3St.js                  16.17 kB │ gzip:   5.28 kB
ℹ dist/hooks-status-DepPyfBb.js              16.07 kB │ gzip:   4.24 kB
ℹ dist/gmail-setup-utils-QpN7TEXS.js         15.38 kB │ gzip:   4.47 kB
ℹ dist/webhooks-cli-D4wyKxFQ.js              14.57 kB │ gzip:   4.00 kB
ℹ dist/systemd-B-3NdMmA.js                   14.35 kB │ gzip:   4.14 kB
ℹ dist/installs-BhEjOqPy.js                  14.05 kB │ gzip:   3.50 kB
ℹ dist/exec-approvals-cli-CWSJ4YSY.js        14.05 kB │ gzip:   3.54 kB
ℹ dist/agent-scope-4nAkb5YL.js               13.38 kB │ gzip:   3.56 kB
ℹ dist/pairing-store-DwvRrpqV.js             11.95 kB │ gzip:   3.13 kB
ℹ dist/skills-cli-ClIV7qUO.js                11.94 kB │ gzip:   2.98 kB
ℹ dist/ws-log-DoIdOhb1.js                    11.83 kB │ gzip:   2.87 kB
ℹ dist/call-DoytZWzC.js                      11.01 kB │ gzip:   3.30 kB
ℹ dist/tailscale-BVGD9gSD.js                  9.01 kB │ gzip:   2.82 kB
ℹ dist/accounts-DkUtJa-O.js                   8.89 kB │ gzip:   2.60 kB
ℹ dist/pi-tools.policy-DdBp13AO.js            8.81 kB │ gzip:   2.44 kB
ℹ dist/update-DzMcwy1G.js                     8.71 kB │ gzip:   2.19 kB
ℹ dist/table-CLtGjVsx.js                      8.48 kB │ gzip:   2.76 kB
ℹ dist/logs-cli-CJoQqrRN.js                   8.33 kB │ gzip:   2.81 kB
ℹ dist/directory-cli-B8fqEnJ8.js              7.90 kB │ gzip:   1.92 kB
ℹ dist/server-node-events-B0DgTW--.js         7.80 kB │ gzip:   2.24 kB
ℹ dist/dns-cli-rINfsSWf.js                    7.79 kB │ gzip:   2.90 kB
ℹ dist/session-key-ezJ78bLC.js                7.68 kB │ gzip:   1.87 kB
ℹ dist/skill-scanner-BoGjHXUZ.js              7.68 kB │ gzip:   2.56 kB
ℹ dist/sqlite-BW8p11HW.js                     7.41 kB │ gzip:   2.49 kB
ℹ dist/skills-status-CEvVUD3U.js              7.29 kB │ gzip:   2.28 kB
ℹ dist/devices-cli-CDVjrGg3.js                7.27 kB │ gzip:   2.20 kB
ℹ dist/exec-HEWTMJ7j.js                       7.16 kB │ gzip:   2.39 kB
ℹ dist/utils-CKSrBNwq.js                      6.83 kB │ gzip:   2.56 kB
ℹ dist/paths-scjhy7N2.js                      6.83 kB │ gzip:   1.95 kB
ℹ dist/auth-CbhB03Rz.js                       6.35 kB │ gzip:   1.80 kB
ℹ dist/shared-BmtNKsPq.js                     5.69 kB │ gzip:   2.04 kB
ℹ dist/docs-cli-Bh1Coji2.js                   5.55 kB │ gzip:   2.02 kB
ℹ dist/pairing-cli-DiHDq_PT.js                5.19 kB │ gzip:   1.93 kB
ℹ dist/widearea-dns-D9Al4QRv.js               5.04 kB │ gzip:   1.93 kB
ℹ dist/nodes-screen-DT5HvhJV.js               4.96 kB │ gzip:   1.32 kB
ℹ dist/auth-health-6GAdWae9.js                4.94 kB │ gzip:   1.51 kB
ℹ dist/net-C8YRVt16.js                        4.39 kB │ gzip:   1.49 kB
ℹ dist/message-channel-Bpfe5l5f.js            4.30 kB │ gzip:   1.28 kB
ℹ dist/progress-xpLtQsNY.js                   4.16 kB │ gzip:   1.38 kB
ℹ dist/rpc-QakyFMzt.js                        4.12 kB │ gzip:   1.74 kB
ℹ dist/github-copilot-token-pGSmVaW-.js       3.97 kB │ gzip:   1.55 kB
ℹ dist/dispatcher-DqwvWXk8.js                 3.93 kB │ gzip:   1.58 kB
ℹ dist/system-cli-CnlB9-gO.js                 3.90 kB │ gzip:   1.19 kB
ℹ dist/redact-DJCFY628.js                     3.62 kB │ gzip:   1.43 kB
ℹ dist/shared-C8_5pNbb.js                     3.21 kB │ gzip:   1.16 kB
ℹ dist/systemd-linger-N-cIaegf.js             3.19 kB │ gzip:   1.01 kB
ℹ dist/cli-CKddHOE-.js                        3.09 kB │ gzip:   1.31 kB
ℹ dist/archive-Dy3Ezb-5.js                    3.00 kB │ gzip:   1.16 kB
ℹ dist/constants-HPrOsATF.js                  2.88 kB │ gzip:   0.79 kB
ℹ dist/path-env-DP3DsVge.js                   2.83 kB │ gzip:   1.11 kB
ℹ dist/tui-cli-DHWbCi4I.js                    2.81 kB │ gzip:   1.30 kB
ℹ dist/openclaw-root-Cvotktkd.js              2.80 kB │ gzip:   0.80 kB
ℹ dist/clack-prompter-CEKDd_Vg.js             2.61 kB │ gzip:   0.86 kB
ℹ dist/note-B5HnoeZX.js                       2.46 kB │ gzip:   0.91 kB
ℹ dist/control-service-DjUCiZsm.js            2.44 kB │ gzip:   0.95 kB
ℹ dist/paths-CR6bsrfc.js                      2.25 kB │ gzip:   0.73 kB
ℹ dist/channel-options-BUbn00Tq.js            2.24 kB │ gzip:   0.92 kB
ℹ dist/node-service-BAYHx0E7.js               2.09 kB │ gzip:   0.62 kB
ℹ dist/channel-selection-BPXp-Ft6.js          2.06 kB │ gzip:   0.73 kB
ℹ dist/command-format-ChfKqObn.js             1.95 kB │ gzip:   0.74 kB
ℹ dist/brew-CAcErcKz.js                       1.65 kB │ gzip:   0.58 kB
ℹ dist/usage-format-DvowRSs-.js               1.50 kB │ gzip:   0.58 kB
ℹ dist/format-B7OjpGnt.js                     1.28 kB │ gzip:   0.61 kB
ℹ dist/parse-log-line-CARp5QyJ.js             1.23 kB │ gzip:   0.52 kB
ℹ dist/env-0_mKbEWW.js                        1.21 kB │ gzip:   0.58 kB
ℹ dist/tailnet-DLDGNuH2.js                    1.21 kB │ gzip:   0.55 kB
ℹ dist/gateway-rpc-CFy1WFmn.js                1.17 kB │ gzip:   0.62 kB
ℹ dist/systemd-hints-DO88c_nD.js              1.11 kB │ gzip:   0.55 kB
ℹ dist/is-main-B6kCyqsv.js                    1.00 kB │ gzip:   0.40 kB
ℹ dist/cli-utils-BkRQdAoC.js                  0.98 kB │ gzip:   0.47 kB
ℹ dist/status-D5UKnMVc.js                     0.97 kB │ gzip:   0.44 kB
ℹ dist/boolean-BgXe2hyu.js                    0.86 kB │ gzip:   0.38 kB
ℹ dist/pi-model-discovery-CV2V1HHz.js         0.84 kB │ gzip:   0.37 kB
ℹ dist/status-tCu4RWZH.js                     0.82 kB │ gzip:   0.35 kB
ℹ dist/deps-DnKN09y7.js                       0.81 kB │ gzip:   0.32 kB
ℹ dist/helpers-5yebzF4C.js                    0.79 kB │ gzip:   0.39 kB
ℹ dist/parse-BZz5lHzQ.js                      0.70 kB │ gzip:   0.36 kB
ℹ dist/help-format-Bozi4K9H.js                0.67 kB │ gzip:   0.30 kB
ℹ dist/transcript-events-ChU6IQwp.js          0.59 kB │ gzip:   0.29 kB
ℹ dist/channels-status-issues-CkX23PyE.js     0.55 kB │ gzip:   0.30 kB
ℹ dist/logging-TXWhN8jG.js                    0.50 kB │ gzip:   0.30 kB
ℹ dist/links-B5pRdmo1.js                      0.49 kB │ gzip:   0.31 kB
ℹ dist/ws-CEcdsnN9.js                         0.47 kB │ gzip:   0.24 kB
ℹ dist/parse-timeout-Du-wHHNi.js              0.46 kB │ gzip:   0.26 kB
ℹ dist/prompt-style-vzh0MGHs.js               0.45 kB │ gzip:   0.25 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js           0.42 kB │ gzip:   0.28 kB
ℹ dist/helpers-CSZtxHTa.js                    0.41 kB │ gzip:   0.26 kB
ℹ dist/pairing-labels-CCiIuKc3.js             0.26 kB │ gzip:   0.18 kB
ℹ dist/prompts-FbZThK8w.js                    0.24 kB │ gzip:   0.17 kB
ℹ dist/logging-BWRYHvLp.js                    0.01 kB │ gzip:   0.03 kB
ℹ 142 files, total: 6043.17 kB
✔ Build complete in 3923ms
ℹ dist/entry.js                              44.79 kB │ gzip:  12.54 kB
ℹ dist/loader-BsYrSp91.js                  2275.04 kB
ℹ dist/gateway-cli-BsiUicCD.js              642.24 kB │ gzip: 150.66 kB
ℹ dist/config-guard-BI-i6Hew.js             227.35 kB │ gzip:  49.42 kB
ℹ dist/config-CVC-02lU.js                   177.14 kB │ gzip:  34.51 kB
ℹ dist/status-C3GkF5iX.js                   119.38 kB │ gzip:  30.79 kB
ℹ dist/manager-BdvAC5a3.js                  118.65 kB │ gzip:  24.62 kB
ℹ dist/onboard-skills-Cjzuu1Aa.js           117.38 kB │ gzip:  25.25 kB
ℹ dist/sandbox-Bx4fVzog.js                  108.29 kB │ gzip:  24.08 kB
ℹ dist/auth-profiles-0bUrpTY2.js            100.74 kB │ gzip:  22.41 kB
ℹ dist/doctor-BprL2ieD.js                    99.75 kB │ gzip:  25.38 kB
ℹ dist/models-cli-CDyjRxY-.js                97.95 kB │ gzip:  22.10 kB
ℹ dist/deliver-BIDW_mg2.js                   84.53 kB │ gzip:  21.11 kB
ℹ dist/tui-uQnn3Xv0.js                       84.02 kB │ gzip:  20.05 kB
ℹ dist/routes-CL5x6Rpf.js                    78.93 kB │ gzip:  15.64 kB
ℹ dist/audit-CmS9aWEu.js                     74.55 kB │ gzip:  18.24 kB
ℹ dist/client-DUpe9pFX.js                    67.03 kB │ gzip:  12.00 kB
ℹ dist/errors-CZ9opC6L.js                    62.00 kB │ gzip:  15.75 kB
ℹ dist/channels-cli-DP18SWYt.js              55.46 kB │ gzip:  14.00 kB
ℹ dist/pw-ai-B7Fvw8DW.js                     54.74 kB │ gzip:  12.64 kB
ℹ dist/health-format-UG0Hrn1r.js             53.14 kB │ gzip:  12.91 kB
ℹ dist/nodes-cli-CzG7n4Ms.js                 51.73 kB │ gzip:  11.18 kB
ℹ dist/node-cli-Dgo-IYAQ.js                  48.70 kB │ gzip:  12.30 kB
ℹ dist/pi-embedded-helpers-U7qcMWTo.js       44.88 kB │ gzip:  11.80 kB
ℹ dist/update-runner-0hp30-vw.js             42.52 kB │ gzip:   9.39 kB
ℹ dist/github-copilot-auth-rIlU5brF.js       40.90 kB │ gzip:   7.87 kB
ℹ dist/update-cli-YMXrxbB4.js                38.79 kB │ gzip:  10.86 kB
ℹ dist/channel-summary-Cq07O8sV.js           36.51 kB │ gzip:   8.48 kB
ℹ dist/hooks-cli-DfNxtINP.js                 35.47 kB │ gzip:   8.12 kB
ℹ dist/configure-ok3Q8yxN.js                 29.85 kB │ gzip:   7.80 kB
ℹ dist/daemon-cli-DgLgnQaa.js                29.78 kB │ gzip:   7.11 kB
ℹ dist/exec-approvals-C-Dx43cR.js            29.48 kB │ gzip:   6.88 kB
ℹ dist/agent-fr7ENtJS.js                     28.82 kB │ gzip:   7.22 kB
ℹ dist/acp-cli-BA2r_kBp.js                   28.73 kB │ gzip:   7.82 kB
ℹ dist/server-context-yKyxyxOJ.js            27.80 kB │ gzip:   7.23 kB
ℹ dist/skills-CmU0Q92f.js                    26.75 kB │ gzip:   6.92 kB
ℹ dist/session-cost-usage-C9bgCj2T.js        25.33 kB │ gzip:   5.95 kB
ℹ dist/cron-cli-Bl_QPfcv.js                  23.56 kB │ gzip:   5.81 kB
ℹ dist/service-_JwSmGSn.js                   23.22 kB │ gzip:   5.55 kB
ℹ dist/onboard-channels-CE22BvSH.js          22.92 kB │ gzip:   5.85 kB
ℹ dist/image-Cx2j94Pk.js                     22.26 kB │ gzip:   6.53 kB
ℹ dist/sandbox-cli-CoDOlOGm.js               21.77 kB │ gzip:   5.62 kB
ℹ dist/qmd-manager-Cbv0THO_.js               20.76 kB │ gzip:   6.10 kB
ℹ dist/manifest-registry-C69Z-I4v.js         20.25 kB │ gzip:   5.07 kB
ℹ dist/service-audit-YyUL5jv1.js             18.65 kB │ gzip:   4.85 kB
ℹ dist/daemon-runtime-CR1S2Y0h.js            18.23 kB │ gzip:   5.09 kB
ℹ dist/plugins-DmOwDqqs.js                   17.93 kB │ gzip:   3.93 kB
ℹ dist/completion-cli-6G_Ii8fY.js            16.66 kB │ gzip:   4.44 kB
ℹ dist/plugin-auto-enable-BEhskCaY.js        16.60 kB │ gzip:   4.30 kB
ℹ dist/tool-display-DmgKs6-V.js              16.39 kB │ gzip:   3.82 kB
ℹ dist/security-cli-CqZ7UaSJ.js              16.17 kB │ gzip:   4.62 kB
ℹ dist/login-qr-DfKzWyRC.js                  16.16 kB │ gzip:   5.27 kB
ℹ dist/plugins-cli-DXwLQnj2.js               16.13 kB │ gzip:   4.42 kB
ℹ dist/hooks-status-CKmUPU-M.js              16.06 kB │ gzip:   4.24 kB
ℹ dist/gmail-setup-utils-Bi6W14MK.js         15.37 kB │ gzip:   4.47 kB
ℹ dist/webhooks-cli-BOlDRyNF.js              14.46 kB │ gzip:   3.95 kB
ℹ dist/systemd-8sIc6isV.js                   14.34 kB │ gzip:   4.12 kB
ℹ dist/installs-DsJkyWfL.js                  14.05 kB │ gzip:   3.50 kB
ℹ dist/exec-approvals-cli-CPeMbvxo.js        13.95 kB │ gzip:   3.50 kB
ℹ dist/agent-scope-xzSh3IZK.js               13.37 kB │ gzip:   3.56 kB
ℹ dist/pairing-store-CDcJ_3K0.js             11.94 kB │ gzip:   3.12 kB
ℹ dist/skills-cli-MAAySMBs.js                11.83 kB │ gzip:   2.93 kB
ℹ dist/ws-log-CPCss-ho.js                    11.82 kB │ gzip:   2.86 kB
ℹ dist/call-DTjuQHyM.js                      11.00 kB │ gzip:   3.30 kB
ℹ dist/register.subclis-DsVgdVQy.js          10.61 kB │ gzip:   2.89 kB
ℹ dist/accounts-MJ4mYpJN.js                   8.84 kB │ gzip:   2.57 kB
ℹ dist/commands-BFN6JELk.js                   8.81 kB │ gzip:   2.43 kB
ℹ dist/update-DNAVcIQ7.js                     8.71 kB │ gzip:   2.20 kB
ℹ dist/table-CJSx0YID.js                      8.47 kB │ gzip:   2.75 kB
ℹ dist/logs-cli-DXq1eZ2S.js                   8.22 kB │ gzip:   2.77 kB
ℹ dist/program-g8XIN3Vo.js                    8.14 kB │ gzip:   3.25 kB
ℹ dist/tailscale-9MusRvOi.js                  8.09 kB │ gzip:   2.48 kB
ℹ dist/directory-cli-C7ukwOrM.js              7.79 kB │ gzip:   1.87 kB
ℹ dist/server-node-events-BlVsV8zt.js         7.68 kB │ gzip:   2.20 kB
ℹ dist/dns-cli-BsOSvdTb.js                    7.68 kB │ gzip:   2.85 kB
ℹ dist/session-key-Dk6vSAOv.js                7.68 kB │ gzip:   1.87 kB
ℹ dist/skill-scanner-Bp1D9gra.js              7.68 kB │ gzip:   2.56 kB
ℹ dist/skills-status-DtXrj3fy.js              7.28 kB │ gzip:   2.27 kB
ℹ dist/run-main-Cv3jOztA.js                   7.25 kB │ gzip:   2.83 kB
ℹ dist/devices-cli-CwKNgw-1.js                7.17 kB │ gzip:   2.15 kB
ℹ dist/exec-B8JKbXKW.js                       7.15 kB │ gzip:   2.38 kB
ℹ dist/sqlite-DODNHWJb.js                     6.67 kB │ gzip:   2.25 kB
ℹ dist/utils-DX85MiPR.js                      6.65 kB │ gzip:   2.47 kB
ℹ dist/auth-DksjO6WG.js                       6.35 kB │ gzip:   1.80 kB
ℹ dist/shared-fnGLWyZ6.js                     5.68 kB │ gzip:   2.03 kB
ℹ dist/docs-cli-BH9bMx3a.js                   5.47 kB │ gzip:   1.98 kB
ℹ dist/pairing-cli-EZUIp4a-.js                5.09 kB │ gzip:   1.88 kB
ℹ dist/widearea-dns-CsSylzXH.js               5.04 kB │ gzip:   1.93 kB
ℹ dist/nodes-screen-DGlNPbk4.js               4.96 kB │ gzip:   1.32 kB
ℹ dist/auth-health-8T7CI5Io.js                4.93 kB │ gzip:   1.50 kB
ℹ dist/net-CWMMy37F.js                        4.39 kB │ gzip:   1.49 kB
ℹ dist/message-channel-BlgPSDAh.js            4.29 kB │ gzip:   1.27 kB
ℹ dist/progress-Da1ehW-x.js                   4.14 kB │ gzip:   1.37 kB
ℹ dist/rpc-C6o61iEs.js                        4.12 kB │ gzip:   1.74 kB
ℹ dist/github-copilot-token-SLWintYd.js       3.96 kB │ gzip:   1.54 kB
ℹ dist/wsl-B6yuTs1k.js                        3.93 kB │ gzip:   1.59 kB
ℹ dist/system-cli-De3tIflY.js                 3.79 kB │ gzip:   1.15 kB
ℹ dist/redact-B8YiFlwn.js                     3.62 kB │ gzip:   1.43 kB
ℹ dist/shared-C1XLEyB0.js                     3.20 kB │ gzip:   1.15 kB
ℹ dist/systemd-linger-SsSOsJST.js             3.19 kB │ gzip:   1.01 kB
ℹ dist/ports-0V-Mu4ch.js                      3.14 kB │ gzip:   1.12 kB
ℹ dist/archive-D0z3LZDK.js                    3.00 kB │ gzip:   1.16 kB
ℹ dist/cli-B4c4E5Cx.js                        2.97 kB │ gzip:   1.27 kB
ℹ dist/constants-D1op9uGI.js                  2.88 kB │ gzip:   0.79 kB
ℹ dist/path-env-h3xp5PqO.js                   2.83 kB │ gzip:   1.10 kB
ℹ dist/openclaw-root-9ILYSmJ9.js              2.80 kB │ gzip:   0.80 kB
ℹ dist/tui-cli-BMrYkt2x.js                    2.71 kB │ gzip:   1.26 kB
ℹ dist/clack-prompter-DuBVnTKy.js             2.60 kB │ gzip:   0.84 kB
ℹ dist/note-Ci08TSbV.js                       2.45 kB │ gzip:   0.90 kB
ℹ dist/control-service-tmird1Ap.js            2.42 kB │ gzip:   0.95 kB
ℹ dist/paths-BhxDUiio.js                      2.24 kB │ gzip:   0.72 kB
ℹ dist/node-service-Lc1LlnFH.js               2.09 kB │ gzip:   0.62 kB
ℹ dist/channel-selection-ucXSmjx7.js          2.06 kB │ gzip:   0.73 kB
ℹ dist/brew-CcZV0dSS.js                       1.65 kB │ gzip:   0.58 kB
ℹ dist/command-format-ayFsmwwz.js             1.58 kB │ gzip:   0.64 kB
ℹ dist/usage-format-E3bMcUMV.js               1.50 kB │ gzip:   0.58 kB
ℹ dist/format-CS7EI0xF.js                     1.28 kB │ gzip:   0.61 kB
ℹ dist/parse-log-line-C6szvNBZ.js             1.23 kB │ gzip:   0.52 kB
ℹ dist/tailnet-Byp3obcc.js                    1.21 kB │ gzip:   0.55 kB
ℹ dist/channel-options-DBFI1YRp.js            1.18 kB │ gzip:   0.56 kB
ℹ dist/gateway-rpc-D5MgIMVs.js                1.17 kB │ gzip:   0.62 kB
ℹ dist/command-options-rFZ_7aaM.js            1.13 kB │ gzip:   0.51 kB
ℹ dist/systemd-hints-Wim4Bq6j.js              1.11 kB │ gzip:   0.55 kB
ℹ dist/is-main-qJ675wPV.js                    1.00 kB │ gzip:   0.40 kB
ℹ dist/cli-utils-ByANh4Sp.js                  0.98 kB │ gzip:   0.47 kB
ℹ dist/status-CuggagUC.js                     0.96 kB │ gzip:   0.43 kB
ℹ dist/pi-model-discovery-DzEIEgHL.js         0.84 kB │ gzip:   0.37 kB
ℹ dist/status-CRIEi8Mc.js                     0.82 kB │ gzip:   0.35 kB
ℹ dist/deps-DWlrptVs.js                       0.81 kB │ gzip:   0.31 kB
ℹ dist/helpers-EKm3X92T.js                    0.79 kB │ gzip:   0.39 kB
ℹ dist/parse-gTOGQPH6.js                      0.70 kB │ gzip:   0.36 kB
ℹ dist/help-format-CfZ94KRN.js                0.66 kB │ gzip:   0.28 kB
ℹ dist/transcript-events-CZ8CG4ht.js          0.59 kB │ gzip:   0.29 kB
ℹ dist/channels-status-issues-NwwdCTbZ.js     0.55 kB │ gzip:   0.30 kB
ℹ dist/links-D0uzJbi6.js                      0.49 kB │ gzip:   0.31 kB
ℹ dist/logging-Cc7m6PTv.js                    0.49 kB │ gzip:   0.29 kB
ℹ dist/ws-D091yo4M.js                         0.47 kB │ gzip:   0.24 kB
ℹ dist/parse-timeout-CbVKLZ4B.js              0.46 kB │ gzip:   0.26 kB
ℹ dist/prompt-style-Dc0C5HC9.js               0.44 kB │ gzip:   0.23 kB
ℹ dist/rolldown-runtime-Cbj13DAv.js           0.42 kB │ gzip:   0.28 kB
ℹ dist/helpers-CeoEYUfW.js                    0.41 kB │ gzip:   0.26 kB
ℹ dist/pairing-labels-bw3QFLZ0.js             0.26 kB │ gzip:   0.19 kB
ℹ dist/prompts-CXLLIBwP.js                    0.24 kB │ gzip:   0.17 kB
ℹ dist/logging-CfEk_PnX.js                    0.01 kB │ gzip:   0.03 kB
ℹ 144 files, total: 6051.28 kB
✔ Build complete in 4188ms

🦞 OpenClaw 2026.2.6-3 (1007d71) — Your inbox, your infra, your rules.

│
◇  
│
◇  
OpenClaw status

Overview
┌─────────────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────┐
│ Item            │ Value                                                                                               │
├─────────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ Dashboard       │ http://127.0.0.1:18789/                                                                             │
│ OS              │ linux 6.17.0-14-generic (x64) · node 22.22.0                                                        │
│ Tailscale       │ off                                                                                                 │
│ Channel         │ dev (main)                                                                                          │
│ Git             │ main · @ 1007d71f                                                                                   │
│ Update          │ available · git main · ↔ origin/main · dirty · behind 53 · npm latest 2026.2.6-3 · deps ok          │
│ Gateway         │ local · ws://127.0.0.1:18789 (local loopback) · reachable 42ms · auth token · ubuntu24mini (10.10.  │
│                 │ 10.34) app unknown linux 6.17.0-14-generic                                                          │
│ Gateway service │ systemd installed · enabled · running (pid 4222, state active)                                      │
│ Node service    │ systemd not installed                                                                               │
│ Agents          │ 1 · 1 bootstrapping · sessions 1 · default main active 1m ago                                       │
│ Memory          │ 0 files · 0 chunks · dirty · sources memory · plugin memory-core · vector ready · fts ready ·       │
│                 │ cache on (0)                                                                                        │
│ Probes          │ skipped (use --deep)                                                                                │
│ Events          │ none                                                                                                │
│ Heartbeat       │ 30m (main)                                                                                          │
│ Sessions        │ 1 active · default gpt-5.1-codex (400k ctx) · ~/.openclaw/agents/main/sessions/sessions.json        │
└─────────────────┴─────────────────────────────────────────────────────────────────────────────────────────────────────┘

Security audit
Summary: 1 critical · 2 warn · 1 info
  CRITICAL Small models require sandboxing and web tools disabled
    Small models (<=300B params) detected: - local-llm/openai/gpt-oss-20b (20B) @ agents.defaults.model.fallbacks (unsafe; sandbox=off; web=[web_fetch, browser]) U…
    Fix: If you must use small models, enable sandboxing for all sessions (agents.defaults.sandbox.mode="all") and disable web_search/web_fetch/browser (tools.deny=["group:web","browser"]).
  WARN Reverse proxy headers are not trusted
    gateway.bind is loopback and gateway.trustedProxies is empty. If you expose the Control UI through a reverse proxy, configure trusted proxies so local-client c…
    Fix: Set gateway.trustedProxies to your proxy IPs or keep the Control UI local-only.
  WARN Some configured models are below recommended tiers
    Smaller/older models are generally more susceptible to prompt injection and tool misuse. - local-llm/openai/gpt-oss-20b (Below GPT-5 family) @ agents.defaults.…
    Fix: Use the latest, top-tier model for any bot with tools or untrusted inboxes. Avoid Haiku tiers; prefer GPT-5+ and Claude 4.5+.
Full report: openclaw security audit
Deep probe: openclaw security audit --deep

Channels
┌──────────┬─────────┬────────┬─────────────────────────────────────────────────────────────────────────────────────────┐
│ Channel  │ Enabled │ State  │ Detail                                                                                  │
├──────────┼─────────┼────────┼─────────────────────────────────────────────────────────────────────────────────────────┤
│ Telegram │ ON      │ OK     │ token config (7835…Pt_4 · len 46) · accounts 1/1                                        │
└──────────┴─────────┴────────┴─────────────────────────────────────────────────────────────────────────────────────────┘

Sessions
┌───────────────────────────────────────────────────────────────────┬────────┬─────────┬───────────────┬────────────────┐
│ Key                                                               │ Kind   │ Age     │ Model         │ Tokens         │
├───────────────────────────────────────────────────────────────────┼────────┼─────────┼───────────────┼────────────────┤
│ agent:main:main                                                   │ direct │ 1m ago  │ gpt-5.1-codex │ 71k/400k (18%) │
└───────────────────────────────────────────────────────────────────┴────────┴─────────┴───────────────┴────────────────┘

FAQ: https://docs.openclaw.ai/faq
Troubleshooting: https://docs.openclaw.ai/troubleshooting

Update available (git behind 53). Run: openclaw update

Next steps:
  Need to share?      openclaw status --all
  Need to debug live? openclaw logs --follow
  Need to test channels? openclaw status --deep
```