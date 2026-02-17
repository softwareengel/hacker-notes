---
title: 
tags: 
date: 2026-02-17
toc: true
toc_sticky: true
---

# 

## History

```
    1  pip install -e .
    2  nanobot onboard
    3  nanobot agent -m "Hello from my local LLM!"
    4  nanobot agent -m "Hello from my local LLM!"
    5  nanobot agent -m "Hello from my local LLM!"
    6  ping 10.10.10.28
    7  ip app 
    8  ip add
    9  ping 10.10.10.28
   10  ping 10.10.10.28
   11  ping 10.10.10.1
   12  wget http://10.10.10.28:1234/v1
   13  cat v1
   14  curl http://localhost:1234/v1/chat/completions   -H "Content-Type: application/json"   -d '{
   15      "model": "google/gemma-3-4b",
   16      "messages": [
   17          {
   18              "role": "system",
   19              "content": "Always answer in rhymes. Today is Thursday"
   20          },
   21          {
   22              "role": "user",
   23              "content": "What day is it today?"
   24          }
   25      ],
   26      "temperature": 0.7,
   27      "max_tokens": -1,
   28      "stream": false
   29  }'
   30  ls
   31  wget http://10.10.10.28:1234/v1
   32  wget http://10.10.10.28:1234/v1
   33  nanobot agent -m "Hello from my local LLM!"
   34  nanobot agent -m "Hello from my local LLM!"
   35  cd ~/.nanobot/
   36  nanobot agent -m "Hello from my local LLM!"
   37  cd /home/ve/src/github/nanobot && python3 -m venv nanobot
   38  git clone https://github.com/HKUDS/nanobot.git
   39  cd nanobot/
   40  pip install -e .
   41  sudo apt install python3-pip
   42  pip install -e .
   43  cd /home/ve/src/github/nanobot && source nanobot/bin/activate
   44  nanobot agent -m "Hello from my local LLM!"
   45  nanobot gateway
   46  nanobot agent
   47  nanobot status
   48  nanobot gateway
   49  nanobot agent
   50  nanobot channels status
   51  nanobot gateway
   52  history
   53  nanobot gateway
   54  nanobot channels status
   55  nanobot
   56  nanobot gateway
   57  ping -c 4 10.10.10.1
   58  history 
   59  nanobot gateway
   60  exit
   61  ls
   62  ls -r
   63  ls -
   64  ls -R
   65  ls -Rb
   66  ls -Rb *.py
   67  ls *.py -Rb 
   68  find /home/ve/src/github/nanobot/nanobot -type f -name "*.py" | xargs wc -l | tail -n1
   69  find /home/ve/src/github/nanobot/nanobot -type f -name "*.py" | xargs wc -l 
   70  find /home/ve/src/github/nanobot/nanobot -type f -name "*.py" -not -path "*/python3.12/*" | xargs wc -l | tail -n1
   71  find /home/ve/src/github/nanobot/nanobot -type f -name "*.py" -not -path "*/python3.12/*" | xargs wc -l 
   72  sudo nextcloud.manual-install ve p
   73  cd /home/ve/src/github/nanobot && source nanobot/bin/activate
   74  nanobot gateway
   75  export LOGURU_LEVEL=DEBUG
   76  python -m nanobot gateway --verbose
   77  htop 
   78  sudo snap remove prometheus
   79  ls -al 
   80  sudo reboot now 
   81  lsblk
   82  sudo resize2fs /dev/sda1
   83  sudo fdisk -l
   84  lsblk
   85  sudo growpart /dev/sda 1
   86  p
   87  htop 
   88  sudo snap stop nextcloud
   89  htop 
   90  sudo snap remove nextcloud 
   91  sudo snap remove prometheus
   92  htop 
   93  ping 10.10.10.1
   94  ping 8.8.8.8.
   95  ping 8.8.8.8
   96  ps
   97  ps -a
   98  ps -ax
   99  htop 
  100  mc
  101  sudo apt install mc
  102  mc
  103  htop 
  104  sudo shutdown now
  105  pnpm openclaw status  
  106  pnpm openclaw logs --follow
  107  pnpm openclaw config set logging.level=trace
  108  pnpm openclaw config set logging.level trace
  109  pnpm openclaw status  Restart the gateway to apply.
  110  pnpm openclaw gateway stop
  111  pnpm openclaw gateway start
  112  pnpm openclaw gateway --verbose --raw-stream --ws-log full
  113  pnpm openclaw logs --follow
  114  pnpm openclaw doctor
  115  pnpm openclaw gateway stop 
  116  pnpm openclaw gateway --verbose --raw-stream --ws-log full
  117  curl -s http://rechenknecht:8000/v1/audio/transcriptions   -F "model=openai/whisper-large-v3"   -F "file=file_8---ff54563f-5bc5-4e08-bd4c-487c0f058fc6.ogg"   -F "language=de"   -F "response_format=verbose_json"
  118  curl -s http://rechenknecht:8000/v1/audio/transcriptions   -F "model=openai/whisper-large-v3"   -F "file=@file_8---ff54563f-5bc5-4e08-bd4c-487c0f058fc6.ogg"   -F "language=de"   -F "response_format=verbose_json"
  119  arp -a
  120  ping rechenknecht 
  121  wget rechenknecht:1234/v1/models
  122  wget rechenknecht:8000
  123  wget rechenknecht:8000/v1
  124  wget rechenknecht:8000/v1/models
  125  curl -s http://rechenknecht:8000/v1/audio/transcriptions   -F "model=openai/whisper-large-v3"   -F "file=file_8---ff54563f-5bc5-4e08-bd4c-487c0f058fc6.ogg"   -F "language=de"   -F "response_format=verbose_json"
  126  curl -s http://rechenknecht:8000/v1/audio/transcriptions   -F "model=openai/whisper-large-v3"   -F "file@=file_8---ff54563f-5bc5-4e08-bd4c-487c0f058fc6.ogg"   -F "language=de"   -F "response_format=verbose_json"
  127  sudo apt install ffmpeg
  128  pip install -U openai-whisper
  129  python3 -m venv whisper-env
  130  source whisper-env/bin/activate
  131  pip install -U openai-whisper
  132  htop 
  133  ps 
  134  ps ex
  135  systemctl --user restart nanobot
  136  ls
  137  source nanobot/bin/activate
  138  cd nanobot/
  139  source nanobot/bin/activate
  140  cd ..
  141  pip install -e .
  142  python3 -m venv .venv
  143  source .venv/bin/activate
  144  pip install -e .
  145  exit
  146  uv venv
  147  python3 -m venv .venv
  148  source .venv/bin/activate
  149  pip install -e .
  150  nanobot onboard
  151  nanobot agent -m "What is 2+2?"
  152  nanobot agent -m "Hello from my local LLM!"
  153  cd /home/ve/src/github/nanobot && source nanobot/bin/activate 
  154  cd /home/ve/src/github/nanobot && source .venv/bin/activate [A
  155  nanobot gateway
  156  nanobot gateway --verbose
  157  exit
  158  chmod +x /tmp/extract_session.sh
  159  /tmp/extract_session.sh
  160  chmod +x ~/create_chat_screenshot.sh
  161* 
  162  cd /home/ve/src/github/openclaw
  163  pnpm openclaw sessions
  164  pnpm openclaw sessions --json
  165  agent:main:mainpnpm openclaw sessions --active 120
  166  pnpm openclaw sessions --active 120
  167  pnpm openclaw sessions --active 1200
  168  for f in ~/.openclaw/agents/codex/sessions/*.jsonl; do   date=$(head -1 "$f" | jq -r '.timestamp' | cut -dT -f1 2>/dev/null || echo "unknown");   size=$(ls -lh "$f" | awk '{print $5}');   echo "$date $size $(basename $f)"; done | sort -r
  169  cd  +
  170  cd ~
  171  ls
  172  sudo apt-get install wkhtmltopdf
  173  wkhtmltoimage --width 1024 --height 60000 http://127.0.0.1:18789/chat ~/openclaw_chat.png
  174  journalctl --user -u openclaw-gateway.service -f
  175  pnpm openclaw gateway --verbose --raw-stream --ws-log full
  176  journalctl --user -u nanobot.service -f
  177  journalctl --user -u nanobot.service -f
  178  systemctl --user restart nanobot
  179  cron 
  180  sudo cron list 
  181  systemctl --user stop nanobot
  182  systemctl --user restart nanobot
  183  systemctl --user stop nanobot
  184  systemctl --user restart nanobot
  185  systemctl --user stop nanobot
  186  systemctl --user restart nanobot
  187  systemctl --user stop nanobot
  188  systemctl --user restart nanobot
  189  systctrl show log
  190  systemctl show log
  191  systemctl list-units --type=service
  192  systemctl list-units --type=service --all
  193  history
  194  systemctl --user restart nanobot
  195  systemctl --user restart openclaw
  196  history |grep claw
  197  journalctl --user -u openclaw-gateway.service -f
  198* 
  199  systemctl --user restart openclaw
  200  systemctl --user restart openclaw.service
  201  systemctl --user restart openclaw-gateway
  202  systemctl --user edit openclaw-gateway
  203  sudo systemctl --user edit openclaw-gateway
  204  systemctl --user edit openclaw-gateway
  205  systemctl --user restart openclaw-gateway
  206  systemctl --user daemon-reload
  207  systemctl --user restart openclaw-gateway
  208  systemctl --user daemon-reload
  209  systemctl --user restart openclaw-gateway
  210  cd /home/ve/src/github/openclaw && pnpm openclaw config set logging.level trace
  211  pnpm openclaw gateway stop
  212  pnpm openclaw gateway start
  213  pnpm openclaw gateway --verbose --raw-stream --ws-log full
  214  systemctl --user stop openclaw-gateway
  215  DEBUG=openclaw:* pnpm openclaw gateway start --verbose
  216  systemctl --user daemon-reload
  217  systemctl --user restart openclaw-gateway.service
  218  systemctl --user daemon-reload
  219  systemctl --user restart openclaw-gateway.service
  220  cls
  221  clear
  222  history
```

## openclaw running config

openclaw.json

```
{

  "meta": {

    "lastTouchedVersion": "2026.2.6-3",

    "lastTouchedAt": "2026-02-16T13:18:27.969Z"

  },

  "wizard": {

    "lastRunAt": "2026-02-16T13:01:31.778Z",

    "lastRunVersion": "2026.2.6-3",

    "lastRunCommand": "doctor",

    "lastRunMode": "local"

  },

  "logging": {

    "level": "trace",

    "redactSensitive": "tools"

  },

  "update": {

    "channel": "stable"

  },

  "models": {

    "providers": {

      "local-llm": {

        "baseUrl": "http://10.10.10.28:1234/v1",

        "apiKey": "none",

        "api": "openai-completions",

        "models": [

          {

            "id": "openai/gpt-oss-20b",

            "name": "openai/gpt-oss-20b",

            "reasoning": false,

            "input": [

              "text"

            ],

            "cost": {

              "input": 0,

              "output": 0,

              "cacheRead": 0,

              "cacheWrite": 0

            },

            "contextWindow": 131072,

            "maxTokens": 81920

          }

        ]

      }

    }

  },

  "agents": {

    "defaults": {

      "model": {

        "primary": "openai/gpt-5-codex",

        "fallbacks": [

          "local-llm/openai/gpt-oss-20b"

        ]

      },

      "models": {

        "openai/gpt-5-codex": {

          "alias": "GPTCodex"

        },

        "openai/gpt-5-mini": {

          "alias": "GPTMini"

        },

        "openai/gpt-5.1": {

          "alias": "GPT51"

        },

        "local-llm/openai/gpt-oss-20b": {

          "alias": "LocalOSS20B"

        }

      },

      "workspace": "/home/ve/.openclaw/workspace",

      "compaction": {

        "mode": "safeguard"

      },

      "maxConcurrent": 4,

      "subagents": {

        "maxConcurrent": 8

      }

    }

  },

  "messages": {

    "ackReactionScope": "group-mentions"

  },

  "commands": {

    "native": "auto",

    "nativeSkills": "auto"

  },

  "channels": {

    "telegram": {

      "enabled": true,

      "dmPolicy": "pairing",

      "botToken": "7835-----wPt_4",

      "groupPolicy": "allowlist",

      "streamMode": "partial"

    }

  },

  "gateway": {

    "port": 18789,

    "mode": "local",

    "bind": "loopback",

    "auth": {

      "mode": "token",

      "token": "25e006-----8ed32bed4b"

    },

    "tailscale": {

      "mode": "off",

      "resetOnExit": false

    },

    "controlUi": {

      "allowInsecureAuth": true

    }

  },

  "plugins": {

    "entries": {

      "telegram": {

        "enabled": true

      }

    }

  }

}
```


## openclaw-gateway.service

~/.config/systemd/user/openclaw-gateway.service


```


[Unit]
Description=OpenClaw Gateway (v2026.2.6-3)
After=network-online.target
Wants=network-online.target

[Service]
ExecStart="/home/ve/.nvm/versions/node/v22.22.0/bin/node" "/home/ve/src/github/openclaw/dist/index.js" gateway --port 18789 "--verbose"
Restart=always
RestartSec=5
KillMode=process
Environment=HOME=/home/ve
Environment="PATH=/home/ve/.nvm/current/bin:/home/ve/.local/bin:/home/ve/.npm-global/bin:/home/ve/bin:/home/ve/.fnm/current/bin:/home/ve/.volta/bin:/home/ve/.asdf/shims:/home/ve/.local/share/pnpm:/home/ve/.bun/bin:/usr/local/bin:/usr/bin:/bin"
Environment=OPENCLAW_GATEWAY_PORT=18789
Environment=OPENCLAW_GATEWAY_TOKEN=25e006414a8799bc561765ead9441cf512cee38ed32bed4b
Environment="OPENCLAW_SYSTEMD_UNIT=openclaw-gateway.service"
Environment=OPENCLAW_SERVICE_MARKER=openclaw
Environment=OPENCLAW_SERVICE_KIND=gateway
Environment=OPENCLAW_SERVICE_VERSION=2026.2.6-3

[Install]
WantedBy=default.target
```


# nanobot

~/.config/systemd/user/nanobot.service
```
[Unit]
Description=Nanobot Service
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
WorkingDirectory=/home/ve/src/github/nanobot
ExecStart=/home/ve/src/github/nanobot/.venv/bin/nanobot gateway --verbose
Restart=always
RestartSec=5
KillMode=process
Environment=HOME=/home/ve
Environment="PATH=/home/ve/src/github/nanobot/.venv/bin:/home/ve/.nvm/current/bin:/home/ve/.local/bin:/usr/local/bin:/usr/bin:/bin"
Environment="VIRTUAL_ENV=/home/ve/src/github/nanobot/.venv"

[Install]
WantedBy=default.target

```

