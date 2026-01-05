# WebCodecs Node.js $10k Challenge

<img width="1025" height="472" alt="image" src="https://github.com/user-attachments/assets/3457c0a5-2ad2-4a28-a1fe-3f518ed5eb3e" />

Video editing is exploding around the world and the potential for it enabled by AI and edge compute is unprecedented. There's finally a good underlying API in the browser for it with [WebCodecs](https://developer.mozilla.org/en-US/docs/Web/API/WebCodecs_API) and high level APIs like [Mediabunny](https://mediabunny.dev/) and [Remotion](https://www.remotion.dev/). But unfortunately you can't easily take the same code written against these and have it run on the server with [Node.js](https://nodejs.org/en).

This is why I'm setting up a challenge to improve the video editing ecosystem. Your objective is to get the [WebCodecs API](https://developer.mozilla.org/en-US/docs/Web/API/WebCodecs_API) running on the server inside of NodeJS.

Since there's only a month for the challenge, it's unlikely that a full working version will be completed. As a result, progress towards that goal will be rewarded. Here are some potential approaches that could be viable:
- Implement the WebCodecs API by forwarding all the calls to the respective calls to ffmpeg via C bindings.
- Extract the WebCodecs implementation from one of the browsers that [currently implement it](https://caniuse.com/webcodecs) in such a way that it can be used standalone.
- Implement a slow but functional JavaScript version of the WebCodecs API.

## Results

When I started the challenge I didn't think that we'd see even one working solution. But when looking at the submissions, I had a hard time evaluating them as they all solved my usecase of running WebCodecs rendering on the server with node. As a result, I'm going to split the $10k prize equally among the 7 entries for $1500 each! I'm hopeful that this challenge is going to spur investment into the world of video editing on the web.

* @Yahweasel [libavjs-webcodecs-polyfill](https://github.com/ennuicastr/libavjs-webcodecs-polyfill) implements WebCodecs through libav.js, which is a port of FFmpeg's library interface to WebAssembly and asm.js. [Submission #1](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/1)
* @boulabiar [webcodecs-node](https://github.com/boulabiar/webcodecs-node) uses node-av for FFmpeg API, skia-canvas for the canvas, and node-webpmux to support WebP. [Submission #3](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/3)
* @remorses [node-libav-webcodecs](https://github.com/remorses/node-libav-webcodecs) provides WebCodecs API polyfill using native Zig bindings to libav (FFmpeg libraries) via NAPI. [Submission #4](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/4)
* @caseymanos [node-webcodecs](https://github.com/caseymanos/node-webcodecs) uses native C++ bindings with Node-API (N-API) for ABI stability, with FFmpeg handling encoding/decoding. [Submission #5](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/5)
* @Vanilagy [webcodecs-polyfill](https://github.com/Vanilagy/webcodecs-polyfill) uses node-av to interface directly with FFmpeg's C API, enabling zero-copy GPU-side transcoding. [Submission #6](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/6)
* @Brooooooklyn [@napi-rs/webcodecs](https://github.com/Brooooooklyn/webcodecs-node) is a Node.js binding using NAPI-RS supporting H.264, H.265, VP8, VP9, AV1, AAC, Opus, MP3, FLAC, Vorbis, ALAC, and PCM. [Submission #7](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/7)
* @pproenca [node-webcodecs](https://github.com/pproenca/node-webcodecs) uses direct FFmpeg C bindings via C++ and N-API, achieving 96.8% test pass rate with built-in Muxer/Demuxer. [Submission #8](https://github.com/vjeux/webcodecs-nodejs-10k-challenge/issues/8)


## Contest

In order to qualify:
- The code must be open sourced.
- The submission must be before **December 31st 2025 Midnight PST** (California time).

To submit your entry, create an issue on this repository with:
- An explanation of what you did.
- How to compile / run it.
- Who are the people that participated. If more than one, how to split the prize between the people if you win.

The **prize pool is $10k** by Christopher "@vjeux" Chedeau. If anyone or a company is interested in contributing more, please reach out at vjeuxx@gmail.com. The judging will happen for a week and **results will be announced Thursday January 8th**. The money will be distributed among the winners at the sole discretion of Christopher Chedeau. If there are no contributions deemed significant enough, part or all the prize pool may not be distributed.
