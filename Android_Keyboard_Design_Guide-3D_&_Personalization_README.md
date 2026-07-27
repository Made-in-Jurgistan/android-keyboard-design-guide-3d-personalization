<div align="center">

# <img src="https://api.iconify.design/lucide:palette.svg?color=%23b25a1a" width="28" height="28" alt="" /> Android Keyboard Design Guide: 3D & Personalization

### The Extension Volume — 3D Rendering · PBR · Custom Themes · Game Engine Bridges

**31 Sections · OpenGL ES · Filament · Unity · Godot · Jetpack Compose · API 30–36**

[![Version](https://img.shields.io/badge/version-2026.2.0-b25a1a?style=flat-square)](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/)
[![License](https://img.shields.io/badge/license-CC%20BY--SA%204.0-b25a1a?style=flat-square)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Accessibility](https://img.shields.io/badge/WCAG-2.2%20AA-b25a1a?style=flat-square)](https://www.w3.org/TR/WCAG22/)
[![Print Ready](https://img.shields.io/badge/print-A4%20ready-b25a1a?style=flat-square)](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/)
[![Companion](https://img.shields.io/badge/companion%20to-Keyboard%20Design%20Guide-b25a1a?style=flat-square)](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide/)

</div>

---

> **3D rendering meets deep personalization** — the complete companion to the Android Keyboard
> Design Guide. Covers OpenGL ES 3D key rendering, Filament PBR materials, GLSL shaders, custom
> theme engines, game engine bridges (Unity, Godot), AI-driven personalization, and production
> performance budgets for GPU-intensive IMEs.

---

## <img src="https://api.iconify.design/lucide:book-open.svg?color=%23b25a1a" width="20" height="20" alt="" /> Table of Contents

| # | Section | Group | Focus |
|---|---------|-------|-------|
| 01 | About This Volume | Orientation | Prerequisites, companion relationship, how to read |
| 02 | Rendering Architecture Overview | Orientation | GPU pipeline, IME rendering constraints, GPU budget |
| 03 | Open Source Reference IMEs | Orientation | Notable projects, architecture lessons |
| 04 | OpenGL ES for Keyboards | 3D Foundations | GLES 3.1+, context creation, shader compilation |
| 05 | GLSurfaceView in IME | 3D Foundations | `GLSurfaceView` lifecycle inside `InputMethodService` |
| 06 | 3D Key Geometry & Meshes | 3D Foundations | Vertex buffers, key meshes, bevel profiles |
| 07 | GLSL Shaders — Depth & Bevel | 3D Foundations | Vertex/fragment shaders, normal mapping, ambient occlusion |
| 08 | Lighting Models for Keys | 3D Foundations | Phong, Blinn-Phong, rim lighting, shadow mapping |
| 09 | Filament Integration | Filament PBR | Google Filament PBR engine in IME, material system |
| 10 | PBR Materials on Keys | Filament PBR | Metallic/roughness workflow, IBL, texture maps |
| 11 | SceneView & Compose Bridge | Filament PBR | `SceneView` Compose integration, scene graph |
| 12 | IBL Environment Lighting | Filament PBR | Image-based lighting, environment maps, diffuse/specular |
| 13 | Canvas + Hardware Acceleration | Custom Rendering | `Canvas` API, hardware layers, `RenderNode` |
| 14 | ComposeUI Shader Effects | Custom Rendering | AGSL (Android Graphics Shading Language), runtime shaders |
| 15 | TextureView Overlay Techniques | Custom Rendering | `TextureView` for video/camera backgrounds |
| 16 | Particle & Ripple Systems | Custom Rendering | Touch feedback, particle emitters, ripple shaders |
| 17 | Custom Layout XML Architecture | Deep Personalization | Per-user layouts, dynamic XML inflation |
| 18 | Per-Key Shape & Geometry | Deep Personalization | Custom key shapes, SVG paths, morphing |
| 19 | Dynamic Theme Engine | Deep Personalization | Runtime theme generation, color extraction, palettes |
| 20 | User-Uploaded Backgrounds | Deep Personalization | Image backgrounds, live wallpaper integration |
| 21 | Sound & Haptic Packs | Deep Personalization | Custom sound sets, haptic patterns, pack format |
| 22 | Font & Label Customization | Deep Personalization | Custom fonts, per-key labels, icon fonts |
| 23 | Unity Android Plugin | Game Engine Bridges | Unity IME plugin, rendering pipeline, input bridge |
| 24 | Godot Android Library | Game Engine Bridges | Godot engine integration, GDScript, Android export |
| 25 | AR Keyboard with Sceneform | Game Engine Bridges | ARCore, depth sensing, spatial key placement |
| 26 | AI-Driven Personalization | Advanced Topics | ML theme suggestions, usage-adaptive layouts |
| 27 | Live Wallpaper Background Keys | Advanced Topics | `WallpaperService`, parallax, GPU rendering |
| 28 | Performance Budgets for 3D | Advanced Topics | GPU time budgets, thermal throttling, fallbacks |
| 29 | QA Checklist — 3D & Visual | Advanced Topics | Visual regression, device matrix, performance gates |
| 30 | Open Source Project Index | Reference | Curated repos, libraries, and tools |
| 31 | References & Further Reading | Reference | Papers, documentation, community resources |

---

## <img src="https://api.iconify.design/lucide:key-round.svg?color=%23b25a1a" width="20" height="20" alt="" /> Key Technologies

| Category | Technologies |
|----------|-------------|
| **3D Rendering** | OpenGL ES 3.1+, `GLSurfaceView`, GLSL ES, vertex/fragment shaders |
| **PBR Engine** | Google Filament, `SceneView`, IBL, metallic/roughness workflow |
| **Game Engines** | Unity (Android plugin), Godot (Android library), ARCore/Sceneform |
| **Custom Rendering** | `Canvas`, `RenderNode`, AGSL (Android Graphics Shading Language), `TextureView` |
| **Personalization** | Dynamic theme engine, custom XML layouts, per-key geometry, SVG paths |
| **Backgrounds** | Live wallpapers, `WallpaperService`, image backgrounds, parallax |
| **Audio/Haptics** | Custom sound packs, haptic patterns, `SoundPool`, `Vibrator` |
| **Fonts** | Custom font integration, icon fonts, per-key label customization |
| **AI** | ML-driven theme suggestions, usage-adaptive layouts, personalization models |
| **Language** | Kotlin, GLSL, AGSL, C++ (JNI), GDScript (Godot) |
| **API Range** | API 30 (minSdk) through API 36 (latest) |

---

## <img src="https://api.iconify.design/lucide:sparkles.svg?color=%23b25a1a" width="20" height="20" alt="" /> Guide Features

- **<img src="https://api.iconify.design/lucide:ruler.svg?color=%23b25a1a" width="16" height="16" alt="" /> Print-Ready** — A4 duplex margins, page-break controls, print-safe color resets
- **<img src="https://api.iconify.design/lucide:accessibility.svg?color=%23b25a1a" width="16" height="16" alt="" /> WCAG 2.2 AA** — Keyboard navigation, skip links, `:focus-visible` outlines, reduced-motion support, forced-colors support
- **<img src="https://api.iconify.design/lucide:search.svg?color=%23b25a1a" width="16" height="16" alt="" /> SEO Optimized** — Open Graph, JSON-LD `TechArticle` structured data, canonical URL
- **<img src="https://api.iconify.design/lucide:palette.svg?color=%23b25a1a" width="16" height="16" alt="" /> Editorial Design** — Lora (display) · DM Sans (body) · JetBrains Mono (code); warm paper palette with burnt sienna accent (`#b25a1a`)
- **<img src="https://api.iconify.design/lucide:smartphone.svg?color=%23b25a1a" width="16" height="16" alt="" /> Responsive** — CSS-only sidebar navigation, mobile hamburger menu, scroll progress indicator
- **<img src="https://api.iconify.design/lucide:zap.svg?color=%23b25a1a" width="16" height="16" alt="" /> Performance** — `content-visibility: auto`, `@property` typed custom properties, layered CSS architecture
- **<img src="https://api.iconify.design/lucide:rainbow.svg?color=%23b25a1a" width="16" height="16" alt="" /> Wide Gamut** — `color-gamut: p3` media query with OKLCH accent colors
- **<img src="https://api.iconify.design/lucide:library.svg?color=%23b25a1a" width="16" height="16" alt="" /> Companion Volume** — Part of the Android Keyboard Design Guide series

---

## <img src="https://api.iconify.design/lucide:rocket.svg?color=%23b25a1a" width="20" height="20" alt="" /> Getting Started

### Read Online

Visit the hosted guide: **[Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization](https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/)**

### Read Locally

```bash
git clone https://github.com/Made-in-Jurgistan/Made-in-Jurgistan.github.io.git
cd Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization
open "Android_Keyboard_Design_Guide-3D_&_Personalization.html"
# or serve locally:
python -m http.server 8000
# navigate to http://localhost:8000
```

### Print to PDF

Open the HTML file in Chrome/Edge → `Ctrl+P` → set paper size to A4 → enable background graphics → print to PDF.

---

## <img src="https://api.iconify.design/lucide:cpu.svg?color=%23b25a1a" width="20" height="20" alt="" /> Rendering Pipeline at a Glance

```text
  ┌──────────────────────────────────────────────────────────────┐
  │                    IME Rendering Stack                        │
  │                                                              │
  │   ┌──────────────┐   ┌─────────────┐   ┌─────────────────┐   │
  │   │  OpenGL ES   │   │   Filament  │   │  Game Engine    │   │
  │   │  GLSL Shaders│   │   PBR IBL   │   │  Unity / Godot  │   │
  │   └──────┬───────┘   └──────┬──────┘   └────────┬────────┘   │
  │          │                  │                    │            │
  │          └────────┬─────────┴───────────────────┘             │
  │                   ▼                                         │
  │          ┌─────────────────────┐                            │
  │          │   GPU Compositor    │                            │
  │          │  (SurfaceFlinger)   │                            │
  │          └────────┬────────────┘                            │
  │                   ▼                                         │
  │          ┌─────────────────────┐                            │
  │          │   Display / Panel   │                            │
  │          └─────────────────────┘                            │
  └──────────────────────────────────────────────────────────────┘
```

---

## <img src="https://api.iconify.design/lucide:library.svg?color=%23b25a1a" width="20" height="20" alt="" /> Related Guides

| Guide | Focus |
|-------|-------|
| **Android Keyboard Design Guide** | Production IME development, API 30–36, Material You 3.0 — **the primary volume** |
| **Mobile STT Engineering Guide** | On-device speech-to-text: audio capture, VAD, model inference, post-processing |
| **Debugging Field Manual** | Cross-platform debugging, AI-augmented workflows, 30 sections |

---

## <img src="https://api.iconify.design/lucide:file-text.svg?color=%23b25a1a" width="20" height="20" alt="" /> Metadata

| Field | Value |
|-------|-------|
| **Author** | Made in Jurgistan |
| **Version** | 2026.2.0 |
| **Published** | 2026-01-15 |
| **Updated** | 2026-01-15 |
| **License** | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) |
| **Accessibility** | WCAG 2.2 AA |
| **Canonical URL** | `https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/` |
| **Theme Color** | `#b25a1a` (Burnt Sienna) |
| **Fonts** | Lora · DM Sans · JetBrains Mono |
| **Series** | Android Keyboard Design Guide (Extension Volume) |

---

## <img src="https://api.iconify.design/lucide:git-pull-request.svg?color=%23b25a1a" width="20" height="20" alt="" /> Contributing

Report issues or suggest improvements: [github.com/Made-in-Jurgistan/android-keyboard-design-guide-3d-personalization-2026/issues](https://github.com/Made-in-Jurgistan/android-keyboard-design-guide-3d-personalization-2026/issues)

---

## <img src="https://api.iconify.design/lucide:scale.svg?color=%23b25a1a" width="20" height="20" alt="" /> License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) — Free to share and adapt with attribution. See [`LICENSE-Keyboard-3D.md`](LICENSE-Keyboard-3D.md) for details.

---

## <img src="https://api.iconify.design/lucide:quote.svg?color=%237c3aed" width="20" height="20" alt="" /> How to Cite

If you reference this guide in academic work, documentation, or project READMEs, please use one of the formats below. Both are consistent with the output generated by GitHub's "Cite this repository" button and the [`cffconvert`](https://github.com/citation-file-format/cffconvert) tool from the repository's `CITATION.cff` file.

### APA (7th Edition)

```text
Made in Jurgistan. (2026). Android Keyboard Design Guide: 3D & Personalization (Version 2026.2.0) [Computer software]. https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/
```

### BibTeX

```bibtex
@software{Made_in_Jurgistan_3D_Personalization_2026,
  author = {Made in Jurgistan},
  month = {1},
  title = {{Android Keyboard Design Guide: 3D & Personalization}},
  url = {https://Made-in-Jurgistan.github.io/android-keyboard-design-guide-3d-personalization/},
  version = {2026.2.0},
  year = {2026}
}
```

> **Note:** A `CITATION.cff` file at the repository root also enables GitHub's built-in "Cite this repository" button (right sidebar on the repo page), which auto-generates APA and BibTeX citations from the same metadata.

---

<div align="center">

**Made in Jurgistan** — Complete Edition · 2026

</div>
