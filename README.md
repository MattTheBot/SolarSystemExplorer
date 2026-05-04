# Solar System Explorer

An interactive 3D solar system you can fly through in your browser.
No installs, no software — just open the link.

**Created by Matthew Thonhauser · School Project**

**[Launch Explorer →](https://mattthebot.github.io/SolarSystemExplorer/)**

---

## Controls

| Input | Action |
|-------|--------|
| WASD / Arrow keys | Fly forward, back, strafe |
| Q / E | Move up / down |
| Hold Shift | 3× speed boost |
| Mouse drag | Look around |
| Scroll | Zoom in / out |
| Click a planet | Camera flies to it |
| Left panel | Select any planet or the Moon |
| Spacebar | Toggle orbital animation on/off |
| Reset View | Return to starting position |
| ⓘ button | Scale & proportions info |

---

## Scale & Proportions

**Planet sizes** are accurately scaled relative to each other.
Earth = 1×, Jupiter = 11.2×, the Sun = 109× Earth's radius.
Roughly 1,000 Jupiters and 1,300,000 Earths fit inside the Sun by volume.

**Orbital distances** use √AU compression so all planets remain visible.
True scale would place Neptune 500 metres from a marble-sized Sun —
everything else would be invisible. The compression preserves the
proportional feel: inner planets are tightly bunched, then a large
gap before Jupiter, then the vast outer system.

| Planet | Real distance | Relative spacing |
|--------|--------------|-----------------|
| Mercury | 0.39 AU | — |
| Venus | 0.72 AU | 1.9× Mercury |
| Earth | 1.00 AU | 2.6× Mercury |
| Mars | 1.52 AU | 3.9× Mercury |
| Jupiter | 5.20 AU | 13× Mercury |
| Saturn | 9.58 AU | 25× Mercury |
| Uranus | 19.2 AU | 50× Mercury |
| Neptune | 30.1 AU | 78× Mercury |

These ratios are reflected in the model's display distances.

**Orbital periods:** when orbits are enabled, 1 real second = 8 simulated Earth days.

---

## Tech

- [Three.js r128](https://threejs.org/) via CDN — WebGL 3D rendering
- GLB planet models in `/planets/` folder
- Single HTML file, zero build tools, works offline once cached

## Hosting

Hosted on [GitHub Pages](https://pages.github.com/) — free static site hosting.
Repository: [github.com/MattTheBot/SolarSystemExplorer](https://github.com/MattTheBot/SolarSystemExplorer)
