# Everything here answers back

Seven interactive elements, hand-written in WebGL. Each one reacts to touch and keeps reacting after you let go.

**[Open the gallery →](https://vladyanya.github.io/everything-answers-back/)**

Designed and coded from scratch by Vladislav Chumachenko · [github.com/vladyanya](https://github.com/vladyanya)

## The elements

| | You do | It answers | Open |
| --- | --- | --- | --- |
| **Water** | touch the pool surface | ripples spread by a wave-equation sim, light catches the caustics | [↗](https://vladyanya.github.io/everything-answers-back/card-water.html) |
| **Prism** | tap the glass | white light runs the rim, splits into a spectrum, and the shape rings | [↗](https://vladyanya.github.io/everything-answers-back/prism.html) |
| **Sky** | blow the wind | cumulus clouds drift and morph along the gust | [↗](https://vladyanya.github.io/everything-answers-back/clouds.html) |
| **Grass** | walk through the field | blades bend under the step and spring back | [↗](https://vladyanya.github.io/everything-answers-back/grass-3d.html) |
| **Wallet** | tap to receive money | the sum is random, the gradient warms toward gold as you get richer | [↗](https://vladyanya.github.io/everything-answers-back/motherlode.html) |
| **Warm** | move across the surface | heat blooms behind the pointer and fades by diffusion | [↗](https://vladyanya.github.io/everything-answers-back/heatmap.html) |
| **Lava** | touch to heat, tap to release a bubble | molten blobs rise, split and merge | [↗](https://vladyanya.github.io/everything-answers-back/lavalamp.html) |

The gallery runs a live preview of every element on its card. Click a card and the full element opens through a soft cross-fade.

## How it is built

Every element is one self-contained HTML file. Open it by double-click and it runs: no build step, no bundler, no dependencies, except three.js on a CDN for the grass.

- **Rendering.** WebGL2, GLSL ES 3.00 fragment shaders, fullscreen-triangle pipeline.
- **Physics.** Ping-pong float textures (RGBA16F, with an RGBA8 fallback when the FBO is unavailable) carry the state between frames: the wave equation in Water, heat diffusion in Warm.
- **Procedural work.** Noise, fbm, domain warping, metaballs, mesh gradients.
- **3D.** three.js r128 with `InstancedMesh` for the grass field.
- **Motion.** Only `transform` and `opacity` are animated, transitions stay short, and `prefers-reduced-motion` turns the decorative motion off.

## Files

```
index.html         gallery: live previews, card tilt and press, fade transition
card-water.html    Water
prism.html         Prism
clouds.html        Sky
grass-3d.html      Grass
motherlode.html    Wallet
heatmap.html       Warm
lavalamp.html      Lava
og.png             social preview
LICENSE            MIT
```

## Run it locally

```bash
git clone https://github.com/vladyanya/everything-answers-back.git
cd everything-answers-back
open index.html
```

Any modern browser with WebGL2 will do. No server is required, the files run straight from disk.

## License

MIT, so you are free to use, study, modify and share this. One ask: keep the copyright notice (`© 2026 Vladislav Chumachenko`) in copies, so authorship stays attached to the work. A link back is appreciated when you build on it.
