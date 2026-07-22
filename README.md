<p align="center">
  <a href="https://postqueen.ai">
    <img src="https://postqueen.ai/icon.svg" width="76" alt="PostQueen" />
  </a>
</p>

<h1 align="center">PostQueen — Docker Compose</h1>

<p align="center">
  <strong>Self-host the open-source, AI-native social media scheduler.</strong><br />
  A ready-to-run Docker Compose stack that pulls the prebuilt PostQueen image — no build step required.
</p>

<p align="center">
  <a href="https://postqueen.ai">Website</a> ·
  <a href="https://github.com/GkhanKINAY/postqueen-app">Application source</a> ·
  <a href="https://github.com/GkhanKINAY/postqueen-helmchart">Kubernetes / Helm</a> ·
  <a href="https://docs.postqueen.ai/configuration/reference">Configuration reference</a> ·
  <a href="https://docs.postqueen.ai">Docs</a>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPL--3.0-blue.svg" alt="License: AGPL-3.0"></a>
  <a href="https://github.com/GkhanKINAY/postqueen-docker-compose/blob/main/docker-compose.yaml"><img src="https://img.shields.io/badge/ghcr.io-postqueen--app%3Alatest-2496ED?logo=docker&logoColor=white" alt="Docker image: ghcr.io/gkhankinay/postqueen-app:latest"></a>
</p>

<p align="center">
  <img alt="X" src="https://postqueen.ai/channel-icons/x.svg" width="28" />
  <img alt="LinkedIn" src="https://postqueen.ai/channel-icons/linkedin.svg" width="28" />
  <img alt="Instagram" src="https://postqueen.ai/channel-icons/instagram.svg" width="28" />
  <img alt="Facebook" src="https://postqueen.ai/channel-icons/facebook.svg" width="28" />
  <img alt="TikTok" src="https://postqueen.ai/channel-icons/tiktok.svg" width="28" />
  <img alt="YouTube" src="https://postqueen.ai/channel-icons/youtube.svg" width="28" />
  <img alt="Threads" src="https://postqueen.ai/channel-icons/threads.svg" width="28" />
  <img alt="Pinterest" src="https://postqueen.ai/channel-icons/pinterest.svg" width="28" />
  <img alt="Reddit" src="https://postqueen.ai/channel-icons/reddit.svg" width="28" />
  <img alt="Bluesky" src="https://postqueen.ai/channel-icons/bluesky.svg" width="28" />
  <img alt="Discord" src="https://postqueen.ai/channel-icons/discord.svg" width="28" />
  <img alt="Slack" src="https://postqueen.ai/channel-icons/slack.svg" width="28" />
  <img alt="Telegram" src="https://postqueen.ai/channel-icons/telegram.svg" width="28" />
  <img alt="Mastodon" src="https://postqueen.ai/channel-icons/mastodon.svg" width="28" />
  <img alt="Twitch" src="https://postqueen.ai/channel-icons/twitch.svg" width="28" />
  <img alt="Kick" src="https://postqueen.ai/channel-icons/kick.svg" width="28" />
  <img alt="Nostr" src="https://postqueen.ai/channel-icons/nostr.svg" width="28" />
  <img alt="Farcaster" src="https://postqueen.ai/channel-icons/warpcast.svg" width="28" />
  <img alt="Lemmy" src="https://postqueen.ai/channel-icons/lemmy.svg" width="28" />
  <img alt="VK" src="https://postqueen.ai/channel-icons/vk.svg" width="28" />
  <img alt="Mewe" src="https://postqueen.ai/channel-icons/mewe.svg" width="28" />
  <img alt="WordPress" src="https://postqueen.ai/channel-icons/wordpress.svg" width="28" />
  <img alt="Medium" src="https://postqueen.ai/channel-icons/medium.svg" width="28" />
  <img alt="Dev.to" src="https://postqueen.ai/channel-icons/devto.svg" width="28" />
  <img alt="Hashnode" src="https://postqueen.ai/channel-icons/hashnode.svg" width="28" />
  <img alt="Dribbble" src="https://postqueen.ai/channel-icons/dribbble.svg" width="28" />
  <img alt="Google Business" src="https://postqueen.ai/channel-icons/google-business.svg" width="28" />
  <img alt="Whop" src="https://postqueen.ai/channel-icons/whop.svg" width="28" />
  <img alt="Skool" src="https://postqueen.ai/channel-icons/skool.svg" width="28" />
  <img alt="Listmonk" src="https://postqueen.ai/channel-icons/listmonk.svg" width="28" />
</p>

---

## About this repository

This repository is the **primary self-host path** for [PostQueen](https://postqueen.ai) — an AI-powered
social media scheduling platform. The included `docker-compose.yaml` pulls the prebuilt application image
[`ghcr.io/gkhankinay/postqueen-app:latest`](https://github.com/GkhanKINAY/postqueen-app) and brings up the
full stack, so there is **no build step**: clone, set a couple of secrets, and `docker compose up -d`.

> PostQueen is a fork of [Postiz](https://github.com/gitroomhq/postiz-app) (AGPL-3.0). Huge thanks to
> Nevo David and the Postiz contributors for the foundation this project stands on. This repository is
> distributed under the [AGPL-3.0](LICENSE) license.

## Prerequisites

- **Docker Engine** 24+
- **Docker Compose v2** (`docker compose`, the plugin — not the legacy `docker-compose` binary)

### System requirements

This stack is **heavy**. Alongside the app it runs a full [Temporal](https://temporal.io) cluster —
Temporal server, its own PostgreSQL, and an Elasticsearch visibility store (its JVM heap is pinned to
~256 MB in the compose file). A small VPS can OOM during startup. Plan for a **multi-GB host**
(roughly **4 GB RAM or more** recommended) with a few GB of free disk for the named volumes.

## Quick start

```bash
git clone https://github.com/GkhanKINAY/postqueen-docker-compose
cd postqueen-docker-compose
docker compose up -d
```

Startup takes a couple of minutes on the first run while Temporal initializes. When the containers are
healthy, open the app at:

```
http://localhost:4007
```

> There is **no TLS** in the default configuration — the app is served over plain **HTTP** on port
> `4007`. Put a reverse proxy (Caddy, nginx, Traefik…) in front of it if you expose it publicly, and
> update the URL variables below to your real, externally reachable address.

## Before your first run

The shipped `docker-compose.yaml` contains **placeholder secrets** meant for local testing only. Change
these before exposing the app to anyone:

- **`JWT_SECRET`** — ships as a literal placeholder (`random string that is unique to every install…`).
  Replace it with your own long, random string. Leaving the placeholder in place is a security hole:
  anyone could forge session tokens.
- **Database password** — the default PostgreSQL password is `postqueen-password`. Change it in the
  `postqueen-postgres` service **and** in the matching `DATABASE_URL` on the app service so they stay in
  sync.

## Required environment

The app is configured entirely through environment variables (see [Configuration](#configuration) for
how to set them). The essentials:

| Variable | Default in compose | What it does |
| --- | --- | --- |
| `MAIN_URL` | `http://localhost:4007` | Public base URL of the app |
| `FRONTEND_URL` | `http://localhost:4007` | Public URL the browser loads |
| `NEXT_PUBLIC_BACKEND_URL` | `http://localhost:4007/api` | Public API base URL used by the frontend |
| `JWT_SECRET` | *(placeholder — change it)* | Signs session tokens; must be unique per install |
| `DATABASE_URL` | `postgresql://postqueen-user:postqueen-password@postqueen-postgres:5432/postqueen-db-local` | PostgreSQL connection string |
| `REDIS_URL` | `redis://postqueen-redis:6379` | Redis connection string |
| `STORAGE_PROVIDER` | `local` | Where uploaded media lives (`local` or `cloudflare`) |

> Point the three URL variables — `MAIN_URL`, `FRONTEND_URL`, and `NEXT_PUBLIC_BACKEND_URL` — at the
> **same externally reachable address** (with `/api` appended for the backend URL). Mismatched URLs are
> the most common cause of a blank screen or login loop.

The full list of every supported variable (social connectors, storage, Stripe, OAuth, short-link
services, and more) lives in the
[configuration reference](https://docs.postqueen.ai/configuration/reference).

## What you get

Bringing the stack up starts these services:

| Service | Image | Exposed on host | Purpose |
| --- | --- | --- | --- |
| `postqueen` | `ghcr.io/gkhankinay/postqueen-app:latest` | **`4007`** | Web UI, API, and Temporal workers |
| `postqueen-postgres` | `postgres:17-alpine` | internal | Application database |
| `postqueen-redis` | `redis:7.2` | internal | Cache & queues |
| `temporal` | `temporalio/auto-setup` | `127.0.0.1:7233` | Workflow engine (scheduling/publishing) |
| `temporal-ui` | `temporalio/ui` | `127.0.0.1:8080` | Temporal dashboard |
| `temporal-postgresql` | `postgres:16` | internal | Temporal's own database |
| `temporal-elasticsearch` | `elasticsearch:7.17` | internal | Temporal visibility store (heap ~256 MB) |
| `temporal-admin-tools` | `temporalio/admin-tools` | internal | Temporal CLI helper |

An optional `spotlight` service for debugging is available under the `debug` Compose profile and is off
by default.

## Data & backups

Application state is kept in named Docker volumes — most importantly:

- `postgres-volume` — the application database
- `postqueen-uploads` — locally stored media (when `STORAGE_PROVIDER=local`)
- `postqueen-config` — app configuration

Back these up (e.g. `docker run --rm -v postgres-volume:/data …`) before upgrades or migrations. Removing
them with `docker compose down -v` deletes all your data. For a complete backup also include
`temporal-postgres-data` (holds in-flight scheduled posts); `postqueen-redis-data` and
`temporal-elasticsearch-data` are caches/indexes and can be recreated.

## Configuration

The containers are configured entirely with environment variables. You can supply them in a few ways:

- **Option A** — inline in the `environment:` blocks of `docker-compose.yaml` (how the file ships).
- **Option B** — a `postqueen.env` file mounted into `/config` for the app container only.
- **Option C** — a `.env` file next to `docker-compose.yaml` (least recommended).

…or a mix of the above. See the
[configuration reference](https://docs.postqueen.ai/configuration/reference) for the
complete list of settings.

## Upgrading

Pull the latest image and recreate the app container:

```bash
docker compose pull
docker compose up -d
```

Review the [migration guide](https://docs.postqueen.ai/installation/migration) before major upgrades in case
migration steps are required.

## Links

- **Website:** [postqueen.ai](https://postqueen.ai)
- **Kubernetes / Helm:** [postqueen-helmchart](https://github.com/GkhanKINAY/postqueen-helmchart)
- **Configuration reference:** [docs.postqueen.ai/configuration/reference](https://docs.postqueen.ai/configuration/reference)
- **Documentation:** [docs.postqueen.ai](https://docs.postqueen.ai)
- **License:** [AGPL-3.0](LICENSE)

## License

This repository is available under the [AGPL-3.0 license](LICENSE).

Original work © Nevo David / Gitroom and the Postiz contributors. Modifications © PostQueen.
