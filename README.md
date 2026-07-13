# Everything here answers back

Interactive WebGL shader gallery — six little "elements" you can touch, and each one responds.

**Author:** Vladislav Chumachenko · designed and coded from scratch · [github.com/vladyanya](https://github.com/vladyanya)

Live: https://everything-answers-back.netlify.app

---

## The elements

| Card | What it does | Verb |
| --- | --- | --- |
| **Water** | Pool surface — touch it, ripples catch the light (wave-equation sim + caustics) | touch |
| **Sky** | Cumulus clouds drift and morph; blow the wind | blow |
| **Grass** | 3D field you can walk through, footprints spring back (three.js) | walk |
| **Wallet** | Tap to receive random money; the gradient warms toward gold as you get richer | tap |
| **Warm** | A living thermal surface; move across it and heat blooms and fades | move |
| **Lava** | Molten wax blobs rise, split and merge; touch to heat, tap to release a bubble | touch |

Click a card → it opens the full interactive element (soft cross-fade). Everything is a single, self-contained HTML file that runs by double-click — no build step, no dependencies except three.js for the grass.

## Tech

- WebGL2 · GLSL ES 3.00 fragment shaders, fullscreen-triangle pipeline
- Ping-pong float textures (RGBA16F) for the physical sims — wave equation (Water), heat diffusion (Warm), FBO fallback to RGBA8
- Procedural noise / fbm / domain warping / metaballs / mesh gradients
- three.js r128 (InstancedMesh) for the 3D grass
- Motion follows productive-animation principles: short opacity transitions, `prefers-reduced-motion` respected, only `transform`/`opacity` animated

## Structure

```
index.html        — landing gallery (live shader previews + tilt/press + fade transition)
card-water.html   — Water
clouds.html       — Sky
grass-3d.html     — Grass
motherlode.html   — Wallet
heatmap.html      — Warm
lavalamp.html     — Lava
LICENSE           — MIT
```

## Using this

Licensed under **MIT** — you're free to use, study, modify and share it. The one ask: **keep the copyright notice** (`© 2026 Vladislav Chumachenko`) in copies, so authorship stays attached to the work. If you build on it, a link back is appreciated.
