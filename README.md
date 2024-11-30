# PixiJS Animated GIF

[![Node.js CI](https://github.com/pixijs-userland/gif/actions/workflows/nodejs.yml/badge.svg?branch=main)](https://github.com/pixijs-userland/gif/actions/workflows/nodejs.yml)

Plugin to support playback of animated GIF images in PixiJS. Unlike normal GIF playback in the browser, this plugins allows you to stop, loop, change speed, or go to a specific frame.

* [Demo](https://userland.pixijs.io/gif/examples/)
* [API Documentation](https://userland.pixijs.io/gif/docs/)

## Usage

Load an animated GIF image with Assets:

```ts
import '@pixi/gif';
import { Assets } from 'pixi.js';

const app = new Application();
const image = await Assets.load('image.gif');
app.stage.addChild(image);
```

To use a gif without Assets:

```ts
import { Application } from 'pixi.js';
import { AnimatedGIF } from '@pixi/gif';

const app = new Application();
fetch('image.gif')
    .then(res => res.arrayBuffer())
    .then(AnimatedGIF.fromBuffer)
    .then(image => app.stage.addChild(image));
```

### Version Compatiblity

| PixiJS | PixiJS GIF |
|--------|------------|
| v6.x   | v1.x       |
| v7.x   | v2.x       |
| v8.x   | v3.x       |
