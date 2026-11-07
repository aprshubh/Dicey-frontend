# Dicey Frontend

A production-oriented React + TypeScript frontend for Dicey.

## Stack
- React 19, TypeScript, Vite
- Tailwind CSS v4, Framer Motion, Lucide
- React Router, TanStack Query, Zustand
- Axios with credentialed HTTP-only cookie sessions
- Zod validation, Vitest

## Run locally
1. Install Node.js 20.19+ or 22.12+.
2. Run `npm install`.
3. Copy `.env.example` to `.env.local` and set `VITE_API_BASE_URL`.
4. Run `npm run dev`.

## Checks
- `npm run typecheck`
- `npm run lint`
- `npm run test`
- `npm run build`

## Current implementation
- Responsive premium-light Dicey shell and dashboard.
- Login, registration and current-session bootstrap wired to verified backend auth endpoints.
- Profile overview.
- Create/join room UI wired to clearly marked proposed endpoint names; these are not treated as implemented APIs and no fake room/game state is generated.

See `docs/API_CONTRACT.md` for verified authentication routes and suggested room/match/realtime contracts. Gameplay UI and realtime integration will follow once backend DTOs and socket events are available.
