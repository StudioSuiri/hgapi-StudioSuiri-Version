# hgapi — StudioSuiri Audit Fork

Fork of [raouldeheer/hgapi](https://github.com/raouldeheer/hgapi).

## Purpose

A Node.js/TypeScript Express API and WebSocket service for exposing and rendering Heroes & Generals strategic war-map information. It includes battle/player/static-information endpoints, strategic route calculation, caching, logging, map serialization and PM2 configuration.

## What it is not

This is a **warmap API / companion service**, not an authoritative first-person-shooter battle server and not the full modern HnG Group/Sunrise backend.

The historical `src/client.ts` calls `Client.connectToHQ`, which fetches `http://game.heroesandgenerals.com/status` and `settings.js`. Those are historical official endpoints; present-day availability and compatibility are not guaranteed. The `/status` route may return 503 when its optional client is disconnected.

The package relies on separately published HAGCP packages (`hagcp-network-client`, `hagcp-assets`, `hagcp-canvas`, `hagcp-utils`). Its test script is a placeholder that exits with an error; do not treat that as a real test suite.

## Build investigation

```bash
npm ci
npm run build
```

Run this in an isolated checkout after verifying Node/TypeScript compatibility. These are suggested commands, not proof of a successful build. Do not deploy with live credentials until endpoint behavior, environment configuration and security have been audited.

## Provenance

- Upstream: https://github.com/raouldeheer/hgapi
- MIT license: [LICENSE](./LICENSE)
- Upstream head observed during audit: `385bb943054a125906ca4494de0066d10197a6e4` (2024-01-24)
- Unified source: [components/hgapi in the HnG research monorepo](https://github.com/StudioSuiri/Heroes-and-Generals-StudioSuiri-Version/tree/audit/consolidate-hng-sources/components/hgapi)
