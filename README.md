# LOS ANGELES — REAL DRIVE

**Build:** 0.1.0 · **Status:** playable technical foundation, not a finished AAA game.

## Run locally

1. Install Python 3 or Node.js.
2. From this folder run `python3 -m http.server 8080` (or `npm run serve`).
3. Open `http://localhost:8080` in a modern browser. Three.js is loaded from jsDelivr, so the first launch requires an internet connection.
4. On Android, open the hosted HTTPS site in Chrome and use **Add to Home screen**. PWA installation requires HTTPS (localhost is exempt for local testing).

## Controls

- W / Up: throttle
- S / Down: brake
- A / Left and D / Right: steering
- Space: handbrake
- C: cycle camera
- Touch: on-screen steering, brake, throttle and handbrake

## Implemented in this build

- Three.js real-time 3D scene and compressed grid-city environment.
- Procedural drivable vehicle meshes and three distinct data-driven vehicle configurations.
- Custom lightweight longitudinal / bicycle-model vehicle dynamics foundation with mass, power, drag, steering, grip and wet-grip adjustment.
- Chase, close cockpit-like and overhead camera modes.
- Basic moving traffic vehicles and adjustable traffic count.
- Time-of-day, weather/fog and wet-grip controls.
- Garage vehicle selection, basic vehicle information, touch controls, HUD, responsive layout and PWA shell caching.
- Initial unit tests for acceleration, braking and vehicle data separation.

## Known limitations — explicitly not implemented yet

This is the first playable engineering foundation, **not** the requested complete simulator. The city is procedural and geographically inspired, not a true Los Angeles road-data recreation. Vehicle meshes are placeholders, not accurate production-year models. Physics is a lightweight custom approximation, not a validated Pacejka tire model or full suspension / drivetrain simulation. Traffic follows simple looping paths, not a lane graph or full traffic AI. Weather controls currently affect fog and approximate wet grip; there is no rain particle or road wetness material system yet. Garage inspection, detailed tuning, localized damage, real vehicle audio, race events, full map navigation, persistent save profiles, and Android APK packaging remain future work. The Three.js runtime is CDN-hosted, so offline cold-start is not guaranteed by the current service worker.

## Architecture

- `src/vehicle-data.js` — data-driven vehicle catalog.
- `src/physics.js` — isolated vehicle dynamics module.
- `src/world.js` — procedural city, lighting, traffic and environment controls.
- `src/main.js` — renderer, input, UI wiring and game loop.
- `tests/physics.test.js` — initial automated physics checks.

## Development principles

All vehicle parameters in this build are explicitly provisional engineering estimates. Replace them with verified data and validated models before treating the simulator as a realistic vehicle-training tool. Keep new systems modular and add automated tests before declaring features complete.
