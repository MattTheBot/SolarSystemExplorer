# Solar System Explorer

Interactive 3D solar system — runs in any browser, hosted on GitHub Pages. No software, no installs.

**[Launch →](https://YOUR-USERNAME.github.io/solar-system/)**

---

## Controls

| Input | Action |
|-------|--------|
| Click a planet | Camera flies smoothly to it |
| Enter orbit range | Info panel appears automatically |
| Scroll | Zoom in / out |

## Scale

**Planet sizes** are accurate relative to each other — Earth = 1×, Jupiter = 11.2×, The Moon = 0.27×.

**Orbital distances** are logarithmically compressed. True scale would put Neptune ~500m from a marble-sized Sun — everything would be invisible. The compression preserves the visual proportions (inner planets close together, giant gap before Jupiter, then vast outer system).

**Orbital periods** are accurate — Mercury completes a lap in 88 simulated days, Neptune in 164.8 years.

## Swapping in your own models

Every planet has a clearly marked comment in `index.html`:

```js
// ┌──────────────────────────────────────────────────────────┐
// │  SWAP MODEL — replace SphereGeometry below with your     │
// │  loaded GLTFLoader mesh, keyed on body.id                │
// └──────────────────────────────────────────────────────────┘
```

To load a GLB file, add this before the BODIES loop:

```html
<script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/loaders/GLTFLoader.js"></script>
```

Then replace the `new THREE.Mesh(new THREE.SphereGeometry(...), ...)` block with:

```js
const loader = new THREE.GLTFLoader();
loader.load('models/earth.glb', gltf => {
  const model = gltf.scene;
  model.scale.setScalar(dispR);
  model.position.x = dispOrbit;
  pivot.add(model);
});
```

## GitHub Pages setup

1. Create a repo (e.g. `solar-system`)
2. Upload `index.html`, `README.md`, `_config.yml`
3. Settings → Pages → source: `main` branch `/`
4. Live in ~60 seconds at `https://YOUR-USERNAME.github.io/solar-system/`

## Tech

- [Three.js r128](https://threejs.org/) via CDN — WebGL rendering
- Vanilla JS, zero build tools, single file
