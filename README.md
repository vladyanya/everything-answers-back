# Everything here answers back

Seven small things you can touch. Water, glass, sky, grass, a wallet, a warm surface, a lava lamp — each one reacts, and keeps reacting after you let go.

**[Open the gallery →](https://vladyanya.github.io/everything-answers-back/)**

I designed and coded them from scratch. Every shader is written by hand, and every element is a single HTML file (double-click it — it runs).

## What's inside

| | You do | It answers | Open |
| --- | --- | --- | --- |
| **Water** | touch the pool surface | ripples spread by a wave-equation sim, light catches the caustics | [↗](https://vladyanya.github.io/everything-answers-back/card-water.html) |
| **Prism** | tap the glass | white light runs the rim, splits into a spectrum, and the shape rings | [↗](https://vladyanya.github.io/everything-answers-back/prism.html) |
| **Sky** | blow the wind | cumulus clouds drift and morph along the gust | [↗](https://vladyanya.github.io/everything-answers-back/clouds.html) |
| **Grass** | walk through the field | blades bend under the step and spring back | [↗](https://vladyanya.github.io/everything-answers-back/grass-3d.html) |
| **Wallet** | tap to receive money | the sum is random, the gradient warms toward gold as you get richer | [↗](https://vladyanya.github.io/everything-answers-back/motherlode.html) |
| **Warm** | move across the surface | heat blooms behind the pointer and fades by diffusion | [↗](https://vladyanya.github.io/everything-answers-back/heatmap.html) |
| **Lava** | touch to heat, tap to release a bubble | molten blobs rise, split and merge | [↗](https://vladyanya.github.io/everything-answers-back/lavalamp.html) |

The gallery is a list on the left and one live stage on the right. Point at a name — the stage switches to that element. Click — it opens full screen, and "back" brings you to the one you left.

On a phone the stage sticks to the top and follows your scroll. First tap shows an element, second tap opens it.

## How it's made

No build step, no bundler, no framework. (The grass is the only one that pulls a library — three.js from a CDN.)

- **Rendering.** WebGL2, GLSL ES 3.00 fragment shaders, one fullscreen triangle.
- **Physics.** Ping-pong float textures (RGBA16F, with an RGBA8 fallback) carry the state from frame to frame — the wave equation in Water, heat diffusion in Warm.
- **Procedural bits.** Noise, fbm, domain warping, metaballs, mesh gradients.
- **3D.** three.js r128 with `InstancedMesh` for the grass field.
- **Motion.** Only `transform` and `opacity` move. With `prefers-reduced-motion` on, the gallery shows still frames and the elements drop the decorative motion.

## Run it locally

```bash
git clone https://github.com/vladyanya/everything-answers-back.git
cd everything-answers-back
open index.html
```

Any modern browser with WebGL2 will do. No server needed — the files run straight from disk.

## Files

```
index.html         the gallery: list of elements, one live stage
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

## License

MIT — use it, take it apart, change it, share it. One ask: keep the copyright line (`© 2026 Vladislav Chumachenko`) in copies, so the work stays signed. A link back is always nice (and if you build something on top — I'd be curious to see it).

Vladislav Chumachenko · [github.com/vladyanya](https://github.com/vladyanya)
