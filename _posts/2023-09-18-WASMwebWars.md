---
created: 2023-09-18T18:36:56+02:00
modified: 2023-09-18T18:39:43+02:00
title: Will WASM win the web wars?
tags:
  - Wasm
  - Web
  - OS
  - Browser
Date: 2024-01-24
date: 2024-06-06
toc: true
toc_sticky: true
---

# From Browser brat to backend boss: Will WASM win the web wars?

Sep-2023: <https://www.theregister.com/2023/09/01/web_assembly_wasm_column/>

2019: <https://hacks.mozilla.org/2019/03/standardizing-wasi-a-webassembly-system-interface/>


Feb-2019 <https://www.theregister.com/2019/03/29/mozilla_wasi_spec/>
- Mozilla tries to do Java as it should have been – with a WASI spec for all devices, computers, operating systems
- One binary to rule them all

## Wasmtime

<https://github.com/bytecodealliance/wasmtime>

wasmtime: A standalone runtime for WebAssembly

A fast and secure runtime for WebAssembly

A [Bytecode Alliance](https://bytecodealliance.org/) project
## bytecodealliance.org

The **Bytecode Alliance** is a nonprofit organization dedicated to creating secure new software foundations, building on standards such as [WebAssembly](https://webassembly.org/) and [WebAssembly System Interface (WASI)](https://wasi.dev).

The Bytecode Alliance is committed to establishing a capable, secure platform that allows application developers and service providers to confidently run untrusted code, on any infrastructure, for any operating system or device, leveraging decades of experience doing so inside web browsers.

We have a [vision](https://bytecodealliance.org/articles/announcing-the-bytecode-alliance) for a secure-by-default WebAssembly ecosystem for all platforms.

<https://bytecodealliance.org/>
<https://github.com/bytecodealliance/>
## WebAssembly Micro Runtime

<https://github.com/bytecodealliance/wasm-micro-runtime>

## WasmEdge

Bring the cloud-native and serverless application paradigms to Edge Computing.

WasmEdge is a lightweight, high-performance, and extensible WebAssembly runtime. It is [the fastest Wasm VM](https://ieeexplore.ieee.org/document/9214403) today. WasmEdge is an official sandbox project hosted by the [CNCF](https://www.cncf.io/). Its [use cases](https://wasmedge.org/book/en/use_cases.html) include modern web application architectures (Isomorphic & Jamstack applications), microservices on the edge cloud, serverless SaaS APIs, embedded functions, smart contracts, and smart devices.

🤩 WasmEdge is the easiest and fastest way to run LLMs on your own devices. 🤩


The WasmEdge Runtime provides a well-defined execution sandbox for its contained WebAssembly bytecode program. The runtime offers isolation and protection for operating system resources (e.g., file system, sockets, environment variables, processes) and memory space. The most important use case for WasmEdge is to safely execute user-defined or community-contributed code as plug-ins in a software product (e.g., SaaS, software-defined vehicles, edge nodes, or even blockchain nodes). It enables third-party developers, vendors, suppliers, and community members to extend and customize the software product. **[Learn more here](https://wasmedge.org/docs/contribute/users)**

<https://www.secondstate.io/articles/wasm-runtime-agi/>

Overview: <https://wasmedge.org/docs/embed/overview/>

<https://wasmedge.org/>
<https://github.com/WasmEdge/WasmEdge>
