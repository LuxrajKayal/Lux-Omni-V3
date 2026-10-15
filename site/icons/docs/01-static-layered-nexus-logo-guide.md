# Lux Omni V3 — The Layered Nexus (Static SVG Architecture)

**The Layered Nexus** translates Lux Omni’s architecture into a strict **7:4 isometric grid** (29.74°, giving exact integer coordinates for crisp pixel-snapping).

## Visual Architecture & Design Logic

1. **Three Stacked Isometric Planes (Extensibility):** Represent your modular layers—**Foundation/Storage** (bottom), **Unified Core** (middle), and **Active Workspace** (top)—floating on a shared vertical axis.
2. **The Split-Workspace "L + O" Top Layer:** Rather than using three identical flat diamonds (which is overused in generic tech logos), the top plane is divided into two interlocking modules:
   * **The Primary "L" Wing (Lux):** Wraps the left and front edges.
   * **The Secondary Workspace Module:** Completes the outer diamond silhouette to form an isometric **"O" (Omni)** while visually representing your **split-screen workspace**.
3. **The Central Nexus Core:** A luminous vertical pillar passes directly through the central aperture of all three layers, symbolizing a unified toolbar and shared state binding independent tools together.

---

## Included Static SVG Files

1. `svg/lux-omni-app-icon.svg` — **Primary Application Icon (`256x256` — Desktop & App Launcher)**: Designed with a deep obsidian-slate squircle container, layered depth gradients, and a glowing cyan-to-indigo nexus core.
2. `svg/lux-omni-flat-symbol.svg` — **Standalone Flat Symbol (`64x64` — Header & Splash Mark)**: Strips away the app container and drop shadows, relying on pure geometric contrast and clean negative space so it works cleanly on both light and dark UI backgrounds.
3. `svg/lux-omni-micro-icon.svg` — **Favicon & UI Toolbar Micro-Icon (`24x24` Optical Size)**: Uses `currentColor` with bold geometric planes and wider negative-space channels so it stays razor-sharp at `16px` to `24px`.

---

## Brand Color & Geometry Tokens

| Element | Role in Identity | Hex Token | Tailwind Equivalent |
| :--- | :--- | :--- | :--- |
| **Lux Cyan (Primary)** | Active "L" workspace plane & clarity accent | `#06B6D4` | `cyan-500` |
| **Sky Module (Secondary)** | Split-screen companion module | `#38BDF8` | `sky-400` |
| **Omni Cobalt (Core)** | Middle unified ecosystem layer | `#2563EB` | `blue-600` |
| **Foundation Slate** | Bottom local/cloud storage layer | `#334155` | `slate-700` |
| **Obsidian Canvas** | Dark-mode application surface | `#0F172A` | `slate-900` |