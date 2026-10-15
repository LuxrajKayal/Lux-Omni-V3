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

---

# Lux Omni V3 — Animated Layered Nexus Loader Guide

Animating **The Layered Nexus** works best when the motion feels engineered and mechanical rather than bouncy. Instead of a generic spinning circle, this animation uses a **2.4-second harmonic cycle** (`cubic-bezier(0.65, 0, 0.35, 1)`) built around three synchronized actions:

1. **Axial Breathing (Z-Axis):** The bottom foundation layer and top workspace layer expand outward along the central vertical axis, then compress back into tight alignment.
2. **Split-Screen Docking (X-Axis):** As the top layer rises, the **Primary "L" Wing** and **Secondary Split Module** separate horizontally along the isometric plane, then snap back together into the unified **"O"** silhouette as the layers lock.
3. **Nexus Core Pulse:** The moment the three planes lock into alignment, an illumination wave travels up the central pillar and flashes the top diamond cap.

---

## Included Animated SVG Files

1. `svg/lux-omni-loader.svg` — **Primary Application & Splash Loader (`256x256`)**: Self-contained SVG using hardware-accelerated CSS transforms (`translate`) and CSS custom properties (`--lux-speed`, `--lux-ease`).
2. `svg/lux-omni-micro-spinner.svg` — **Compact Toolbar & Tab Micro-Spinner (`24x24`)**: Uses a staggered vertical wave (`0.18s` phase offset per plane) and inherits your button or text color via `currentColor`.

---

## Controlling Loader State in Your UI

Because the animation rests in its locked, aligned position at both `0%` and `85%–100%` of the keyframe timeline, you can transition smoothly from **Loading** to **Ready** without a jarring visual jump:

* **Adjusting Speed Dynamically:** Override `--lux-speed` on the parent container (for example, `--lux-speed: 1.4s` during intensive file exports).
* **Locking on Completion:** When your workspace finishes initializing, apply `animation-iteration-count: 1` to the SVG elements so the current cycle finishes snapping into the unified nexus position and comes to a clean stop.