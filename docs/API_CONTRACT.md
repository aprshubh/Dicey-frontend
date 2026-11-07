# Dicey API contract

Base URL: VITE_API_BASE_URL (default http://localhost:4000/api/v1). Verified routes below are present in current backend. Proposed names are suggestions only, not implemented.

## Verified auth routes

| Method | Path | Body |
|---|---|---|
| POST | /auth/register | { name, email, password } |
| POST | /auth/login | { email, password } |
| POST | /auth/logout | Cookie session |
| POST | /auth/refresh-token | Refresh cookie/body |
| POST | /auth/forgot-password | { email } |
| POST | /auth/reset-password | { token, newPassword } |
| GET | /auth/me | Current user |
| PATCH | /auth/me | { name? } |
| POST | /auth/change-password | { currentPassword, newPassword } |
| POST | /auth/logout-all | Revoke sessions |

Auth response shape: { success, message, data: { user, tokens } }. Backend uses HTTP-only access/refresh cookies; Axios uses withCredentials. Do not persist refresh tokens in localStorage. Password requirements: 8-100 characters, uppercase, lowercase, digit and special character.

## Proposed room/game endpoints — backend pending

| Method | Suggested path | Purpose |
|---|---|---|
| POST | /rooms | Create: { maxPlayers, visibility, controlMode } |
| POST | /rooms/join | Join: { code } |
| GET | /rooms/:roomId | Room/player snapshot |
| POST | /rooms/:roomId/leave | Leave room |
| POST | /rooms/:roomId/start | Host starts match |
| GET | /rooms/:roomId/state | Authoritative state |
| POST | /matchmaking/queue | Enter quick match queue |
| DELETE | /matchmaking/queue | Leave queue |
| GET | /users/me/stats | Player statistics |

Suggested socket events: room:join, room:leave, room:state, room:member-joined, room:member-left, game:started, game:roll, game:move, game:state, game:error. Server must own dice, turns, legal moves, captures and victory. Confirm transport, DTOs, auth, reconnect and events before gameplay wiring.

Never fabricate room IDs, players, dice or game state. Production CORS must allow exact deployed frontend HTTPS origin with credentials.