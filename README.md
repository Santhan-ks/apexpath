# APEXPATH

A hackathon frontend prototype for coordinating mixed-fleet last-mile deliveries in Chennai. The repeatable demo includes one warehouse, two four-wheelers, three two-wheelers, two relay points, and twelve orders.

## Features

- Nine-page operations workspace with dashboard metrics, partner and vehicle registries, orders, routing, tracking, handovers, analytics, and settings.
- Interactive Chennai map with vehicle and delivery markers, route filters, camera controls, and 3D buildings where vector tile data supports them.
- Partner and vehicle registration, order creation, capacity-aware assignment, delivery updates, and relay handover recording.
- Pausable GPS/GSM simulation, home-bound route sequencing, and browser-persisted display preferences.
- Lightweight vehicle-loading introduction with skip and reduced-motion support.

## Stack

React, TypeScript, Vite, MapLibre GL JS with OpenFreeMap tiles, Lucide React, custom CSS, and Oxlint. Routing tests use Node's built-in test runner. No API keys, database, or authentication backend are required.

## Run locally

Use Node.js 24 and npm. From the project directory:

```sh
npm ci
npm run dev
```

Open the local URL printed by Vite. For a loopback-only server, run `npm run dev -- --host 127.0.0.1`.

## Validate and build

```sh
npm run typecheck
npm run lint
npm test
npm run build
npm run preview
```

The build includes TypeScript checks and writes production assets to `dist/`. The preview command serves that build locally; it is not a production hosting service.

## Demo limitations

- GPS positions, GSM connection states, and relay handovers are simulated. No physical devices, live traffic, or machine-learning predictions are connected.
- Routing uses a deterministic capacity-aware assignment and nearest-neighbor heuristic. Lines are schematic connections; distances are approximate straight-line estimates, not road navigation or a certified global optimum. Comparisons use the same assigned workload and distance model.
- Partner, vehicle, order, and handover changes live in application memory and reset on reload. Settings use browser local storage; intro completion uses session storage.
- Map tiles and optional Google Fonts require internet access. The map provides a schematic fallback when tiles fail and reports unsupported WebGL; other operations remain available.
- Capacity figures include upstream relay freight allocations and downstream courier workloads. They represent planned route-leg allocation, not a live measurement of onboard cargo.

This prototype was developed with AI assistance. Submission-specific disclosure requirements should be followed.
