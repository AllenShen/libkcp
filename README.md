# libkcp
[![Powered][1]][2] [![Build Status][3]][4]
[1]: https://img.shields.io/badge/KCP-Powered-blue.svg
[2]: https://github.com/skywind3000/kcp
[3]: https://travis-ci.org/xtaci/libkcp.svg?branch=master
[4]: https://travis-ci.org/xtaci/libkcp
kcp client session library for iOS/Android, compatible with [kcp-go](https://github.com/xtaci/kcp-go).

## Features
1. Optimized for Real-Time Strategy Game.
2. No Forward Error Correction(FEC).
3. No Packet Level Encryption.
4. Abstraction on Stream(```ReadWriter``` interface).
5. Less than 300 LOC, just copy ```sess.cpp sess.h``` to your projects and play.

## Usage
libkcp was designed as a Frame-Driven library, the main loop was supposed as:
```
WHILE(NOT GAMEOVER) DO      // e.g:  A 30FPS Game
       Network.Read()
       Network.Write()
       Network.Update()
       GameLogic()
       GameRender()
       Wait(33ms)   // frame ticker
END
```

```Read/Write/Update``` are guaranteed to be non-blocking.

Please read ```main.cpp``` for library usage.

## Troubleshooting
1. C++11 is required for compiling.
2. Make sure you are using ```Listen()``` function in kcp-go.
