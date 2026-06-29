# Ascent AR — ASCEND Horizon Europe

WebXR augmented reality viewer for the ASCEND citizen engagement project in Munich's Harthof/Hasenbergl neighborhood.

**Live:** https://jawhar00.github.io/Ascent-AR/

---

## What it does

Points your phone camera at the real neighborhood and overlays 3D models of planned energy transition measures at their real-world GPS locations:

| Stop | Location | Description |
|---|---|---|
| 🌿 Parklet | 48.203062, 11.568186 | Community parklet with herb garden |
| 🔌 EV-Carport | 48.20383, 11.56543 | Solar carport with charging stations |
| 🏗 Sanierung | 48.20478, 11.56758 | Building energy refurbishment |
| 🏢 Mehrfamilienhaus | 48.20372, 11.57315 | Multi-family building with tenant power |
| 🏠 Neubau KfW-40 | 48.20313, 11.57122 | Plus-energy new build quarter |

---

## How to use

1. Open the URL on an **Android phone** in **Chrome**
2. Tap **AR starten** — allow camera and location permissions
3. Walk around Harthof — 3D models appear at their real locations
4. Tap **🧪 Testmodus** to preview the parklet model 10m in front of you (works indoors)

**Requirements:** Android + Chrome + ARCore support

---

## Tech stack

- [Three.js 0.170](https://threejs.org/) — 3D rendering
- WebXR `immersive-ar` — ARCore integration
- `GLTFLoader` — GLB model loading
- Browser Geolocation API — GPS positioning
- `deviceorientationabsolute` — compass north alignment

---

## Project structure

```
index.html          # Main AR viewer (GPS mode + test mode)
mindar.html         # MindAR QR image-tracking fallback
parklet_blender.glb # Parklet 3D model (Blender export)
ev_carport.glb      # EV carport model
refurbishment.glb   # Refurbishment building model
mw_building.glb     # Multi-family building model
targets.mind        # MindAR compiled image targets
```

---

## Known limitations

- GPS accuracy is ±10–30m — models may drift from exact real-world position
- Works on Android Chrome only (WebXR `immersive-ar` not supported on iOS)
- GLB models load asynchronously — teal beacon appears first while loading

---

## Part of

[ASCEND Horizon Europe](https://ascend-project.eu/) — Spatial Intelligence Track  
TUM-XR Hub · Supervisor: Joel Christlein  
© GeodatenService München (GSM) data attribution required on all outputs
