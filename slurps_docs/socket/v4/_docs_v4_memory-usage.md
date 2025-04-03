---
url: https://socket.io/docs/v4/memory-usage
scrapeDate: 2025-04-03T05:03:01.306Z
library: v4

exactVersionMatch: false
---

The resources consumed by your Socket.IO server will mainly depend on:
*   the number of connected clients
*   the number of messages ([basic emit](_docs_v4_emitting-events_.md#basic-emit), [emit with acknowledgement](_docs_v4_emitting-events_.md#acknowledgements) and [broadcast](_docs_v4_broadcasting-events_.md)) received and sent per second

info

The memory usage of the Socket.IO server should scale **linearly** with the number of connected clients.

tip

By default, a reference to the first HTTP request of each session is kept in memory. This reference is needed when working with `express-session` for example (see [here](_how-to_use-with-express-session.md)), but can be discarded to save memory:
```
io.engine.on("connection", (rawSocket) => {  
  rawSocket.request = null;});  
```
The source code to reproduce the results presented in this page can be found [there](https://github.com/socketio/socket.io-benchmarks).

See also:
*   [Load testing](_docs_v4_load-testing_.md)
*   [Performance tuning](_docs_v4_performance-tuning_.md)

The memory usage of the Socket.IO server heavily depends on the memory usage of the underlying WebSocket server implementation.

The chart below displays the memory usage of the Socket.IO server, from 0 up to 10 000 connected clients, with:
*   a Socket.IO server based on the [`ws`](https://github.com/websockets/ws) package (used by default)
*   a Socket.IO server based on the [`eiows`](https://github.com/mmdevries/eiows) package, a C++ WebSocket server implementation (see [installation steps](_docs_v4_server-installation_.md#other-websocket-server-implementations))
*   a Socket.IO server based on the [`µWebSockets.js`](https://github.com/uNetworking/uWebSockets.js) package, a C++ alternative to the Node.js native HTTP server (see [installation steps](_docs_v4_server-installation_.md#usage-with-uwebsockets))
*   a plain WebSocket server based on the [`ws`](https://github.com/websockets/ws) package

![Chart of the memory usage per WebSocket server implementation](https://socket.io/assets/images/memory-usage-per-impl-0f33f953418d9d533b3c996ea134bc96.png)

Tested on `Ubuntu 22.04 LTS` with Node.js `v20.3.0`, with the following package versions:
*   `socket.io@4.7.2`
*   `eiows@6.7.2`
*   `uWebSockets.js@20.33.0`
*   `ws@8.11.0`

The chart below displays the memory usage of the Socket.IO server over time, from 0 up to 10 000 connected clients.

![Chart of the memory usage over time](https://socket.io/assets/images/memory-usage-over-time-79ea9e6413d1fb93cfc2f5e9cf2d7c82.png)

note

For demonstration purposes, we manually call the garbage collector at the end of each wave of clients:
```
io.on("connection", (socket) => {  
  socket.on("disconnect", () => {    const lastToDisconnect = io.of("/").sockets.size === 0;    if (lastToDisconnect) {      gc();    }  });});  
```
Which explains the clean drop in memory usage when the last client disconnects. This is not needed in your application, the garbage collection will be automatically triggered when necessary.