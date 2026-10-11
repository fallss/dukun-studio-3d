# 🔮 Dukun — Gen Z Ritual Studio (3D Interactive Experience)

[![Live Demo](https://img.shields.io/badge/Demo-Live%20Website-ff0055?style=for-the-badge&logo=vercel&logoColor=white)](https://dukun-studio-3d-5qdqov7zl-ifhal-faizi.vercel.app/)
[![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Three.js](https://img.shields.io/badge/Three.js-r180-000000?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org/)
[![R3F](https://img.shields.io/badge/@react--three/fiber-v9.3-blue?style=for-the-badge&logo=threedotjs&logoColor=white)](https://docs.pmnd.rs/react-three-fiber/)
[![GSAP](https://img.shields.io/badge/GSAP-ScrollTrigger-88CE02?style=for-the-badge&logo=greensock&logoColor=white)](https://gsap.com/)
[![Vite](https://img.shields.io/badge/Vite-7.1-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)

> **Live Demo:** [https://dukun-studio-3d-5qdqov7zl-ifhal-faizi.vercel.app/](https://dukun-studio-3d-5qdqov7zl-ifhal-faizi.vercel.app/)

---

## 📖 Overview

**Dukun — Gen Z Ritual Studio** is an immersive, scroll-driven 3D web experience that bridges centuries-old Indonesian folklore and traditional mysticism with hyper-modern creative web development and digital culture.

Built with **React 19**, **Three.js**, **React Three Fiber (R3F)**, **Drei**, **GSAP ScrollTrigger**, and **Lenis Scroll**, the website delivers a seamless narrative journey across a candlelit chamber, a mystical thin-film soap bubble, and an interactive 3D collection of ritual artifacts (Keris, Boneka, Tarot, Jenglot).

---

## 🌐 Live Preview

You can experience the production deployment directly on Vercel:
👉 **[dukun-studio-3d-5qdqov7zl-ifhal-faizi.vercel.app](https://dukun-studio-3d-5qdqov7zl-ifhal-faizi.vercel.app/)**

---

## ✨ Key Features & Creative Architecture

### 1. 🕯️ Atmospheric 2.5D Volumetric Stage
- **Cinematic Chamber**: Procedurally mapped room with candlelit warmth, dark foreground falloff, and subtle drifting incense smoke.
- **Relief & Normal Mapping**: Custom analytical depth and normal maps (`character-depth.jpg`, `character-normal.jpg`) sculpt realistic shadows on 2.5D plates based on user cursor coordinates without requiring heavy 3D character meshes.
- **Tone Preservation**: Bypasses generic ACES tone mapping to preserve the rich, saturated Indonesian batik pigments and warm skin tones.

### 2. 🫧 Thin-Film Interference Bubble Shader
- **Spectral Optics**: Custom shader modeling thin-film light interference, Fresnel edge distortion, and studio reflections.
- **Dynamic Interaction**: Interactive pointer deformation and touch ripple effect that seamlessly transitions into the core scroll zoom.
- **FBO Optimization**: Single-pass environment reflection capture avoids costly multi-pass cube camera re-renders.

### 3. 📜 Precision Scroll-Driven Storytelling
- **360vh Scrub Journey**: Powered by GSAP ScrollTrigger synchronized with Lenis smooth scrolling (1.8s scrub duration).
- **Single Source of Truth**: `src/journey.js` manages camera zoom trajectories, copy reveals, object containment boundaries, and gallery spread coordinates.
- **Single Render Loop Ownership**: GSAP updates interaction progress while the R3F frame loop exclusively controls camera positions, avoiding stutter or frame desynchronization.

### 4. 🗡️ Interactive 3D Artifacts Showcase
- **Curated 3D Models**: Real-time rendering of authentic ritual objects:
  - **Keris**: Sacred wavy-blade dagger.
  - **Tarot**: Mystical divination cards.
  - **Boneka Ritual**: Handcrafted effigy.
  - **Jenglot**: Cryptid talisman artifact.
- **Bounded Physics**: Artifacts float organically inside conservative bounding spheres and spread outward into the gallery upon entering the bubble.
- **Asset Compression**: Geometry compressed with **Google DRACO** and textures formatted with **KTX2 / Basis Universal** for lightning-fast network delivery.

### 5. ♿ Accessibility & Performance First (A11y & Core Web Vitals)
- **Reduced Motion Support**: Detects `prefers-reduced-motion` to disable aggressive pinning and ambient spinning while ensuring all text and gallery controls remain fully readable and interactive.
- **Modal Focus Management**: Accessible detail panels with keyboard trap, `Escape` key dismissal, and scroll lock.
- **Hardware Adaptability**: Automatic DPR scaling via `@react-three/drei`'s `PerformanceMonitor` and graceful HTML/CSS fallback if WebGL2 is unsupported.

---

## 🛠️ Tech Stack & Libraries

| Technology | Purpose |
| :--- | :--- |
| **React 19** | Modern UI composition, state management, and lifecycle hooks |
| **Three.js & R3F** | Declarative 3D WebGL scene graph and shader programming |
| **@react-three/drei** | High-level 3D helpers (Environment, PerformanceMonitor, useGLTF) |
| **GSAP & ScrollTrigger** | High-performance scrubbed timelines and scroll pinning |
| **@studio-freight/lenis** | Smooth momentum-based inertial scrolling |
| **DRACO & KTX2 / Basis** | High-efficiency 3D mesh and texture compression pipeline |
| **Vite 7** | Ultra-fast build tool and local development server |
| **Vercel** | Edge deployment and global CDN hosting |

---

## 📂 Project Architecture

```plaintext
Dukun-website/
├── public/
│   ├── basis/                 # KTX2 / Basis Universal transcoders
│   ├── draco/                 # Google DRACO geometry decoders
│   ├── editorial/             # Rendered transparent portrait stills
│   ├── props/                 # Optimized .glb models & props metadata
│   └── textures/              # Depth, normal, and atmospheric textures
├── scripts/
│   ├── hero-maps.mjs          # Procedural depth/normal map generator
│   ├── room-maps.mjs          # Room perspective depth computation
│   ├── render-portraits.mjs   # Headless portrait renderer
│   └── smoke.mjs              # End-to-end smoke test suite
├── src/
│   ├── Hero3D.jsx             # 3D stage, volumetric figure, and bubble shader
│   ├── Scene.jsx              # Main R3F Canvas, lighting, raycasting & models
│   ├── journey.js             # Scroll progress coordinates & story beats
│   ├── scrollState.js         # Singleton reactive state for scroll & pointer
│   ├── main.jsx               # Root DOM layer, dialogs, nav, and booking UI
│   └── style.css              # Typography, layout tokens, and responsive styles
├── CARA_MENJALANKAN.md        # Panduan lokal dalam Bahasa Indonesia
├── index.html                 # HTML entry point with semantic metadata
├── package.json               # Dependencies & scripts
└── vite.config.js             # Vite configuration with React plugin
```

---

## 🚀 Getting Started

### Prerequisites
- **Node.js**: `v18.0.0` or higher (Disarankan Node.js `v20 LTS`)
- **npm**: `v9.0.0` or higher

### 1. Clone Repository
```bash
git clone https://github.com/fallss/dukun-studio-3d.git
cd dukun-studio-3d
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run Development Server
```bash
npm run dev
```
Open **[http://localhost:5173](http://localhost:5173)** in your browser.

### 4. Build for Production
```bash
npm run build
```
Build output will be bundled in the `dist/` directory.

### 5. Preview Production Build
```bash
npm run preview
```

---

## 🧪 Testing

The repository includes a standalone automated smoke test suite:
```bash
npm test
```
Tests verify bundle integrity, 3D asset decodability, and key story beat interactions.

---

## 📄 License & Attribution

- Artwork, character plate, and 3D props are created for this demonstration.
- Atmospheric room shader techniques adapted under MIT license from the Yakudoo Halloween reference (stored in `public/licenses/yakudoo-halloween.txt`).
- Created with passion for creative web development.
