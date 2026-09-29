# RS Digital Agency Automation

A small TypeScript API foundation for coordinating work across RS CSC Centre, RS Digital Agency, and Candid Frame Studio. This starter currently supports authenticated task intake and listing. It does **not** send messages, process payments, or connect to government services.

## Requirements

- Node.js 20 or newer and npm

## Local setup

```bash
npm ci
cp .env.example .env
# Replace API_KEY in .env with a random secret of at least 32 characters.
set -a; source .env; set +a
npm run dev
```

On Windows PowerShell, set `NODE_ENV`, `HOST`, `PORT`, and `API_KEY` as environment variables before `npm run dev`; this starter does not load `.env` automatically.

The server defaults to `127.0.0.1:3000`. Verify `GET /health`, then use `x-api-key` for `/api/v1/tasks`:

```bash
curl -H "x-api-key: $API_KEY" -H 'content-type: application/json' \
  -d '{"title":"Prepare client proposal","brand":"rs-digital-agency"}' \
  http://127.0.0.1:3000/api/v1/tasks
```

## Commands

| Command | Purpose |
| --- | --- |
| `npm run dev` | Restart the API on source changes |
| `npm run check` | Typecheck, test, and build |
| `npm start` | Run compiled JavaScript after build |

## Project layout

| Path | Purpose |
| --- | --- |
| `src/config.ts` | Environment validation |
| `src/app.ts` | HTTP routes and request validation |
| `src/server.ts` | Process entry point and shutdown |
| `tests/` | API behavior tests |
| `docs/` | Architecture, security, and roadmap |
| `.github/workflows/ci.yml` | Automated checks |

## Deployment status

This is a deployable **foundation**, not a production data store. Tasks are held in memory and disappear on restart. Before real customer use, add persistent storage, migration and backup procedures, per-user authorization, audit logging, and a deployment secret manager. Keep the API behind HTTPS and restrict access. See [architecture](docs/ARCHITECTURE.md), [security](docs/SECURITY.md), and [roadmap](docs/ROADMAP.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). No license has been granted; contact the repository owner before reuse outside this project.
