# Dicey Frontend

Production-oriented frontend for Dicey, a multiplayer Ludo game.

> Backend integration is intentionally contract-driven. Only verified backend endpoints are enabled; planned endpoints are documented in `docs/API_CONTRACT.md` and are not simulated.

## Stack
- React 19 + TypeScript + Vite
- Tailwind CSS
- React Router
- TanStack Query
- Zustand
- Axios + Zod
- Vitest + Testing Library

## Local development
1. `npm install`
2. Copy `.env.example` to `.env.local` and set `VITE_API_BASE_URL`.
3. `npm run dev`

## Quality checks
- `npm run typecheck`
- `npm run lint`
- `npm run test`
- `npm run build`

See `docs/API_CONTRACT.md` for verified and proposed API contracts.
