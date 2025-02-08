---
created: 2023-09-18T18:15:53+02:00
modified: 2023-09-18T18:15:55+02:00
title: Chrome DevTools Protocol
tags:
  - Chrome
Date: 2024-01-24
---
# Chrome DevTools Protocol

<https://chromedevtools.github.io/devtools-protocol/>

The Chrome DevTools Protocol allows for tools to instrument, inspect, debug and profile Chromium, Chrome and other Blink-based browsers. Many existing projects currently use the protocol. The Chrome DevTools uses this protocol and the team maintains its API.

Instrumentation is divided into a number of domains (DOM, Debugger, Network etc.). Each domain defines a number of commands it supports and events it generates. Both commands and events are serialized JSON objects of a fixed structure. 

## Screenshot - Function 
```
You can also issue your own commands using Protocol Monitor. If the command does not require any parameters, type the command into the prompt at the bottom of the Protocol Monitor panel and press Enter, for example, `Page.captureScreenshot`. If the command requires parameters, provide them as JSON, for example, `{"cmd":"Page.captureScreenshot","args":{"format": "jpeg"}}`.
```

## Screenshot 

![](../_asset/2023-09-18-18-15-53_Chrome%20DevTools%20Protocol_image_1.jpg)
