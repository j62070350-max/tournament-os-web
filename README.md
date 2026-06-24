# tournament-os-web — Web API & Dashboard

FastAPI web API and organizer dashboard. Deployed on **Vercel**.

## Deploy on Vercel

1. [vercel.com](https://vercel.com) → **Add New Project** → import this repo
2. Framework Preset: **Other**
3. Add environment variables:

```
DATABASE_URL=postgresql://...
ADMIN_DASHBOARD_TOKEN=<long random string>
SECRET_KEY=<another long random string>
GROQ_API_KEY=your_groq_key
ENVIRONMENT=production
```

4. Click **Deploy** — Vercel auto-detects `vercel.json` ✅

## API Endpoints

| Route | Auth | Description |
|-------|------|-------------|
| `GET /` | None | Dashboard homepage |
| `GET /dashboard` | None | Organizer dashboard UI |
| `GET /healthz` | None | Health check |
| `GET /api/public/tournaments` | None | Public tournament list |
| `GET /api/dashboard/*` | Bearer token | Admin endpoints |
| `POST /api/ai/chat` | None | AI assistant |

## Database Migrations

After first deploy, run once:
```bash
DATABASE_URL=your_postgres_url alembic upgrade head
```

## Discord Bots
Live in **[tournament-os](https://github.com/j62070350-max/tournament-os)** → deployed on Railway.
