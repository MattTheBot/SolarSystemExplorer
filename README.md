# Solar System Explorer - https://mattthebot.github.io/SolarSystemExplorer/

Interactive 3D solar system

## Scale

**Planet sizes** are accurate relative to each other — Earth = 1×, Jupiter = 11.2×, The Moon = 0.27×.

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

## Credit

- [Three.js r128](https://threejs.org/) via CDN — WebGL rendering
- Vanilla JS, zero build tools, single file
