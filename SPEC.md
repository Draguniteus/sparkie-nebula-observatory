# Sparkie Nebula Observatory — SPEC.md

## Concept & Vision

A celestial observatory floating at the heart of a living nebula. Sparkie perches at the center of the cosmos — surrounded by swirling cosmic gases, distant stars, orbiting celestial bodies, and ancient star charts projected in holographic light. This is where Sparkie watches over the universe. Dreamy, majestic, infinite.

## Design Language

**Aesthetic:** Cosmic dreamscape — rich nebula colors against deep space blacks. Ethereal glow, soft god-rays, particle dust. Royal but mystical.

**Color Palette:**
- Deep Space: `#0a0612`
- Nebula Purple: `#6b2d8c`
- Cosmic Pink: `#e84a8a`
- Cyan Glow: `#00e5ff`
- Star White: `#f0f6ff`
- Gold Accent: `#ffd700`
- Soft Lavender: `#c9a0ff`

**Typography:** Cinzel (headers) + Rajdhani (UI overlays) — regal + futuristic

**Motion Philosophy:**
- Slow, graceful orbits of celestial bodies (0.1-0.3 rad/s)
- Pulsing nebula glow (sine wave, 2-4s period)
- Drifting star particles (parallax layers)
- Telescope gentle rotation tracking cursor
- Holographic star charts flicker softly

## Layout & Structure

**Scene Hierarchy:**
1. **Space Background** — Deep black with subtle gradient to deep purple
2. **Star Field** — 3 parallax layers of procedural stars (near/mid/far)
3. **Nebula Cloud** — Procedural volumetric shader with multiple color lobes
4. **Observatory Platform** — Central floating structure, hexagonal, glowing edges
5. **Telescope Array** — Main telescope on platform, rotates toward cursor
6. **Orbiting Planets** — 3 small celestial bodies in elliptical orbits
7. **Holographic Star Charts** — Floating ring of holographic constellation maps
8. **Sparkie Presence** — Subtle sparkle particle system emanating from center
9. **Cosmic Dust** — Fine particle system drifting through scene

## Features & Interactions

**Camera:** OrbitControls with auto-rotate (0.5 rad/s), damping enabled. Mouse orbit on drag.

**Telescope Tracking:** On mouse move, telescope pivots smoothly toward cursor position (lerp factor 0.05).

**Holographic Charts:** Rotate slowly, flicker opacity between 0.6-1.0.

**Orbiting Bodies:** 3 planets in elliptical orbits at different speeds and inclinations.

**Nebula Pulse:** Nebula color intensity oscillates gently.

**Auto-Demo Mode:** If no interaction for 10s, camera slowly circles the scene.

**Performance:** Target 60fps on mobile. Instanced geometry for stars/particles. Shader-based nebula.

## Component Inventory

- **StarField**: 3 layers, instanced points, varying sizes and brightness
- **NebulaCloud**: Custom fragment shader, 3 color lobes, animated noise
- **ObservatoryPlatform**: Hexagonal prism, glowing edges (LineSegments), metallic material
- **Telescope**: Cylinder + cone geometry, pivots on Y axis, subtle glow
- **OrbitalPlanets**: Sphere geometry with emissive materials, trail effect
- **HoloCharts**: Plane geometry with custom holographic shader, rotating ring formation
- **ParticleSystems**: PointsMaterial with custom sprites, drift motion
- **SparkieSparkles**: Bright point sprites emanating from center platform

## Technical Approach

- Three.js r160 via CDN (importmap)
- Single HTML file with inline JS/CSS
- OrbitControls for camera
- Custom GLSL shaders for nebula and holographic effects
- InstancedMesh for star fields and particles
- RequestAnimationFrame render loop with delta time
- Responsive canvas, full-viewport
- OG meta tags for Telegram link previews
