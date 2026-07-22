<p align="center">
  <a href="https://postqueen.ai">
    <img src=".github/assets/header.svg" width="840" alt="PostQueen self-host (Docker Compose)" />
  </a>
</p>

<h3 align="center">🆕&nbsp; NEW: the PostQueen <a href="https://postqueen.ai/agent">Agent CLI</a> + <a href="https://postqueen.ai/mcp">MCP server</a>: plug Claude&nbsp;Code, ChatGPT, Cursor, OpenClaw, Hermes or Codex straight into your channels.</h3>

<br/>

<div align="center">
  <h2>Self-host the queen of your posts 👑</h2>
  <p>
    She writes, designs and schedules across <strong>30+ networks</strong>. You just approve,<br/>
    all on your own server, and <strong>nothing goes out without your say-so</strong>.
  </p>
  <p><em>An open-source alternative to Buffer, Hootsuite, Sprout Social and Later.</em></p>
</div>

<br/>

<p align="center">
  <a href="https://postqueen.ai">Website</a> &nbsp;·&nbsp;
  <a href="https://postqueen.ai/pricing">Pricing</a> &nbsp;·&nbsp;
  <a href="https://app.postqueen.ai/auth">Start free</a> &nbsp;·&nbsp;
  <a href="https://docs.postqueen.ai">Docs</a> &nbsp;·&nbsp;
  <a href="https://docs.postqueen.ai/configuration/reference">Configuration reference</a> &nbsp;·&nbsp;
  <a href="https://github.com/GkhanKINAY/postqueen-helmchart">Helm</a>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPL--3.0-blue.svg" alt="License: AGPL-3.0"></a>
  <a href="https://github.com/GkhanKINAY/postqueen-docker-compose/blob/main/docker-compose.yaml"><img src="https://img.shields.io/badge/ghcr.io-postqueen--app%3Alatest-2496ED?logo=docker&logoColor=white" alt="Docker image: ghcr.io/gkhankinay/postqueen-app:latest"></a>
  <a href="https://github.com/GkhanKINAY/postqueen-helmchart"><img src="https://img.shields.io/badge/Helm-Kubernetes-0F1689?logo=helm&logoColor=white" alt="Helm chart for Kubernetes"></a>
</p>

<br/>

<p align="center">
  <img src=".github/assets/channels.svg" width="780" alt="Supported social networks" />
</p>

<p align="center">
  <a href="https://docs.postqueen.ai"><strong>Explore the docs »</strong></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://postqueen.ai/pricing"><strong>Start a 7-day free trial »</strong></a>
</p>

<br/>

> PostQueen is a fork of [Postiz](https://github.com/gitroomhq/postiz-app) (AGPL-3.0). Huge thanks to Nevo David and the Postiz contributors for the foundation this project stands on.

---

## 🐳 Self-host PostQueen with Docker Compose

This repository is the **primary self-host path** for [PostQueen](https://postqueen.ai), the open-source, AI-native social media scheduler that publishes to **30+ social networks**. The included `docker-compose.yaml` pulls the prebuilt application image [`ghcr.io/gkhankinay/postqueen-app:latest`](https://github.com/GkhanKINAY/postqueen-app) and brings up the whole stack, so there is **no build step**: clone, set a couple of values inline, and run `docker compose up -d`.

> **☁️ Prefer zero setup?** This stack is powerful but heavy (see [System requirements](#-system-requirements) below). Skip it entirely and start a **[7-day free trial](https://postqueen.ai/pricing)**: the managed cloud runs everything for you, and you are posting in minutes with nothing to maintain.

<br/>

---

## 📋 Prerequisites

- **Docker Engine** 24 or newer
- **Docker Compose v2** (the `docker compose` plugin, not the legacy `docker-compose` binary)

<br/>

---

## 🧰 System requirements

This stack is **heavy**. Alongside the app it runs a full [Temporal](https://temporal.io) cluster: the Temporal server, its own PostgreSQL, and an Elasticsearch visibility store (its JVM heap is pinned to roughly 256 MB in the compose file). A small VPS can OOM during startup. Plan for a **multi-GB host** (about **4 GB of RAM or more** recommended) with a few GB of free disk for the named volumes.

> **☁️ Don't want to run all this?** Start a **[7-day free trial](https://postqueen.ai/pricing)** instead. The managed cloud runs the entire stack (Postgres, Redis, and the full Temporal cluster) for you, so you can be posting in minutes with nothing to provision or babysit.

<br/>

---

## 🚀 Quick start

All configuration lives **inline in `docker-compose.yaml`**. There is no `.env.example` to copy: you edit the `environment:` blocks directly, then bring the stack up.

```bash
git clone https://github.com/GkhanKINAY/postqueen-docker-compose
cd postqueen-docker-compose

# Open docker-compose.yaml and, before your first run, set:
#   1. JWT_SECRET      : replace the placeholder with a long, unique random string
#   2. your public URLs: MAIN_URL, FRONTEND_URL, NEXT_PUBLIC_BACKEND_URL
#                        (only needed if you expose the app beyond localhost)

docker compose up -d
```

The first run takes a couple of minutes while Temporal initializes. Once the containers are healthy, open the app at:

```
http://localhost:4007
```

> ⚠️ There is **no TLS** in the default configuration: the app is served over plain **HTTP** on port `4007`. Put a reverse proxy (Caddy, nginx, Traefik, and so on) in front of it if you expose it publicly, and point the URL variables at your real, externally reachable address.

<br/>

---

## 🔧 Before your first run

The shipped `docker-compose.yaml` contains **placeholder secrets** meant for local testing only. Change these before exposing the app to anyone:

- **`JWT_SECRET`** ships as a literal placeholder (`random string that is unique to every install...`). Replace it with your own long, random string. Leaving the placeholder in place is a security hole: anyone could forge session tokens.
- **Database password** defaults to `postqueen-password`. Change it in the `postqueen-postgres` service **and** in the matching `DATABASE_URL` on the app service so the two stay in sync.

<br/>

---

## ⚙️ Required environment

The app is configured entirely through environment variables, set inline in the `environment:` block of the `postqueen` service. The essentials:

| Variable | Default in compose | What it does |
| --- | --- | --- |
| `MAIN_URL` | `http://localhost:4007` | Public base URL of the app |
| `FRONTEND_URL` | `http://localhost:4007` | Public URL the browser loads |
| `NEXT_PUBLIC_BACKEND_URL` | `http://localhost:4007/api` | Public API base URL used by the frontend |
| `JWT_SECRET` | *(placeholder, change it)* | Signs session tokens, must be unique per install |
| `DATABASE_URL` | `postgresql://postqueen-user:postqueen-password@postqueen-postgres:5432/postqueen-db-local` | PostgreSQL connection string |
| `REDIS_URL` | `redis://postqueen-redis:6379` | Redis connection string |
| `STORAGE_PROVIDER` | `local` | Where uploaded media lives (`local` or `cloudflare`) |

> Point the three URL variables (`MAIN_URL`, `FRONTEND_URL`, and `NEXT_PUBLIC_BACKEND_URL`) at the **same externally reachable address**, with `/api` appended for the backend URL. Mismatched URLs are the most common cause of a blank screen or a login loop.

The full list of every supported variable (social connectors, storage, Stripe, OAuth, short-link services, and more) lives in the [configuration reference](https://docs.postqueen.ai/configuration/reference).

<br/>

---

## 📦 What you get

Bringing the stack up starts these services:

| Service | Image | Exposed on host | Purpose |
| --- | --- | --- | --- |
| `postqueen` | `ghcr.io/gkhankinay/postqueen-app:latest` | **`4007`** | Web UI, API, and Temporal workers |
| `postqueen-postgres` | `postgres:17-alpine` | internal | Application database |
| `postqueen-redis` | `redis:7.2` | internal | Cache and queues |
| `temporal` | `temporalio/auto-setup` | `127.0.0.1:7233` | Workflow engine (scheduling and publishing) |
| `temporal-ui` | `temporalio/ui` | `127.0.0.1:8080` | Temporal dashboard |
| `temporal-postgresql` | `postgres:16` | internal | Temporal's own database |
| `temporal-elasticsearch` | `elasticsearch:7.17` | internal | Temporal visibility store (heap about 256 MB) |
| `temporal-admin-tools` | `temporalio/admin-tools` | internal | Temporal CLI helper |

An optional `spotlight` service for debugging is available under the `debug` Compose profile and is off by default.

<br/>

---

## 💾 Data and backups

Application state is kept in named Docker volumes, most importantly:

- `postgres-volume`: the application database
- `postqueen-uploads`: locally stored media (when `STORAGE_PROVIDER=local`)
- `postqueen-config`: app configuration

Back these up (for example with `docker run --rm -v postgres-volume:/data ...`) before upgrades or migrations. Removing them with `docker compose down -v` deletes all your data. For a complete backup also include `temporal-postgres-data` (it holds in-flight scheduled posts). The `postqueen-redis-data` and `temporal-elasticsearch-data` volumes are caches and indexes that can be recreated.

<br/>

---

## 🔀 Configuration

Configuration is set inline in `docker-compose.yaml`. You can supply the variables in a few ways:

- **Inline** in the `environment:` blocks of `docker-compose.yaml` (how the file ships).
- **A mounted env file**, such as `postqueen.env` mounted into `/config` for the app container.
- **A `.env` file** next to `docker-compose.yaml` (least recommended).

See the [configuration reference](https://docs.postqueen.ai/configuration/reference) for the complete list of settings.

<br/>

---

## ⬆️ Upgrading

Pull the latest image and recreate the app container:

```bash
docker compose pull
docker compose up -d
```

Review the [migration guide](https://docs.postqueen.ai/installation/migration) before major upgrades in case migration steps are required.

<br/>

---

## ☸️ Kubernetes

Prefer to run PostQueen on Kubernetes instead of Docker Compose? Use the official Helm chart: [postqueen-helmchart](https://github.com/GkhanKINAY/postqueen-helmchart).

<br/>

---

## 🔗 Links

- **Website:** [postqueen.ai](https://postqueen.ai)
- **Cloud and 7-day trial:** [postqueen.ai/pricing](https://postqueen.ai/pricing)
- **Start free:** [app.postqueen.ai/auth](https://app.postqueen.ai/auth)
- **Application source:** [postqueen-app](https://github.com/GkhanKINAY/postqueen-app)
- **Kubernetes / Helm:** [postqueen-helmchart](https://github.com/GkhanKINAY/postqueen-helmchart)
- **Configuration reference:** [docs.postqueen.ai/configuration/reference](https://docs.postqueen.ai/configuration/reference)
- **Documentation:** [docs.postqueen.ai](https://docs.postqueen.ai)

<br/>

---

## ❤️ Community & Support

We would love to hear from you, whether you hit a bug, have an idea, or just want to say hi:

- 🐛 **Found a bug or have a feature idea?** [Open an issue](https://github.com/GkhanKINAY/postqueen-docker-compose/issues).
- 💌 **Need a hand?** Email **support@postqueen.ai**.
- 📚 **Getting started?** The [docs](https://docs.postqueen.ai) walk you through everything.

If PostQueen saves you time, a ⭐ on the repo genuinely helps other people find it.

## License

This repository is available under the [AGPL-3.0 license](LICENSE).

Original work © Nevo David / Gitroom and the Postiz contributors. Modifications © PostQueen.
