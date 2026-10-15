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