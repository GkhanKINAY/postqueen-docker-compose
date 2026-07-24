<p align="center">
  <a href="https://postqueen.ai">
    <img src=".github/assets/header.svg?v=6" width="840" alt="PostQueen, the queen of your posts, your AI social media assistant" />
  </a>
</p>

<h3 align="center">
  <a href="https://postqueen.ai/agent">🆕 NEW: meet the PostQueen Agent, run your social media from Claude Code, ChatGPT, OpenClaw or Hermes »</a>
</h3>

<br/>

<p align="center">
  <strong>Stop doing social media yourself.</strong>
</p>

<p align="center">
  PostQueen is an AI employee for your social media. Tell her what to share, in one sentence. She writes the copy, designs the visual and schedules it on every channel you have. You just review the calendar.
</p>

<p align="center">
  <strong>Views on autopilot. Posts every day. Launches everywhere.</strong><br/>
  <em>All while you do your actual job.</em>
</p>

<p align="center">
  <strong><a href="https://postqueen.ai">PostQueen</a></strong> is the open-source alternative to <strong>Buffer, Hootsuite, Sprout Social</strong> and <strong>Later</strong>.
</p>

<br/>

<p align="center"><img src=".github/assets/divider.svg" width="840" alt="" /></p>

<br/>

<p align="center">
  <a href="https://postqueen.ai">Website</a> &nbsp;·&nbsp;
  <a href="https://postqueen.ai/pricing">Pricing</a> &nbsp;·&nbsp;
  <a href="https://docs.postqueen.ai">Docs</a> &nbsp;·&nbsp;
  <a href="https://api.postqueen.ai/docs">API Reference</a> &nbsp;·&nbsp;
  <a href="https://postqueen.ai/agent">Agents</a> &nbsp;·&nbsp;
  <a href="https://postqueen.ai/mcp">MCP</a> &nbsp;·&nbsp;
  <a href="https://www.npmjs.com/package/postqueen">CLI</a>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPL--3.0-blue.svg" alt="License: AGPL-3.0"></a>
  <a href="https://github.com/GkhanKINAY/postqueen-docker-compose/blob/main/docker-compose.yaml"><img src="https://img.shields.io/badge/ghcr.io-postqueen--app%3Alatest-2496ED?logo=docker&logoColor=white" alt="Docker image: ghcr.io/gkhankinay/postqueen-app:latest"></a>
</p>

<br/>

<p align="center">
  <!-- CHANNEL ICONS: 30 individual imgs, natural flow, mobile-wrap -->
  <img src=".github/assets/channels/instagram.svg" height="44" alt="Instagram" /> <img src=".github/assets/channels/youtube.svg" height="44" alt="YouTube" /> <img src=".github/assets/channels/google-business.svg" height="44" alt="Google Business Profile" /> <img src=".github/assets/channels/dribbble.svg" height="44" alt="Dribbble" /> <img src=".github/assets/channels/linkedin.svg" height="44" alt="LinkedIn" /> <img src=".github/assets/channels/reddit.svg" height="44" alt="Reddit" /> <img src=".github/assets/channels/tiktok.svg" height="44" alt="TikTok" /> <img src=".github/assets/channels/facebook.svg" height="44" alt="Facebook" /> <img src=".github/assets/channels/pinterest.svg" height="44" alt="Pinterest" /> <img src=".github/assets/channels/threads.svg" height="44" alt="Threads" /> <img src=".github/assets/channels/x.svg" height="44" alt="X" /> <img src=".github/assets/channels/slack.svg" height="44" alt="Slack" /> <img src=".github/assets/channels/discord.svg" height="44" alt="Discord" /> <img src=".github/assets/channels/mastodon.svg" height="44" alt="Mastodon" /> <img src=".github/assets/channels/bluesky.svg" height="44" alt="Bluesky" /> <img src=".github/assets/channels/lemmy.svg" height="44" alt="Lemmy" /> <img src=".github/assets/channels/warpcast.svg" height="44" alt="Farcaster" /> <img src=".github/assets/channels/telegram.svg" height="44" alt="Telegram" /> <img src=".github/assets/channels/nostr.svg" height="44" alt="Nostr" /> <img src=".github/assets/channels/vk.svg" height="44" alt="VK" /> <img src=".github/assets/channels/devto.svg" height="44" alt="Dev.to" /> <img src=".github/assets/channels/medium.svg" height="44" alt="Medium" /> <img src=".github/assets/channels/hashnode.svg" height="44" alt="Hashnode" /> <img src=".github/assets/channels/wordpress.svg" height="44" alt="WordPress" /> <img src=".github/assets/channels/whop.svg" height="44" alt="Whop" /> <img src=".github/assets/channels/kick.svg" height="44" alt="Kick" /> <img src=".github/assets/channels/mewe.svg" height="44" alt="MeWe" /> <img src=".github/assets/channels/twitch.svg" height="44" alt="Twitch" /> <img src=".github/assets/channels/listmonk.svg" height="44" alt="Listmonk" /> <img src=".github/assets/channels/skool.svg" height="44" alt="Skool" />
</p>


<br/>

<p align="center"><img src=".github/assets/divider.svg" width="840" alt="" /></p>

<br/>

<h3 align="center">Schedule and generate posts with AI</h3>

<p align="center">
  <img src=".github/assets/calendar.svg" width="660" alt="The PostQueen calendar: a week of posts across your channels, with AI generation and drag to reschedule" />
</p>

<br/>

<p align="center">
  <strong>Free for 7 days in the cloud. Forever free on your own server.</strong>
</p>

<p align="center">
  <a href="https://postqueen.ai"><img src=".github/assets/cta-cloud.svg" height="52" alt="Start free for 7 days" /></a>
  &nbsp;&nbsp;
  <a href="#-quick-start"><img src=".github/assets/cta-selfhost.svg" height="52" alt="Self-host it free" /></a>
</p>

<br/>

---

## 🐳 What you are deploying

[PostQueen](https://github.com/GkhanKINAY/postqueen-app) is an open-source AI social media assistant: it writes, schedules and publishes your posts to 30+ networks. This repository is its primary self-host path: a single `docker-compose.yaml` that pulls the prebuilt image [`ghcr.io/gkhankinay/postqueen-app:latest`](https://github.com/GkhanKINAY/postqueen-app) and brings up the whole stack, the app itself plus PostgreSQL, Redis and a full [Temporal](https://temporal.io) cluster for scheduling, with no build step. Fair warning: that Temporal cluster makes the stack heavy, so plan for a host with 4 GB of RAM or more. In exchange, self-hosting is completely free with no channel limits: every connector and every feature, on your own hardware.

---

## ✅ Prerequisites

- **Docker Engine** 24 or newer
- **Docker Compose v2** (the `docker compose` plugin, not the legacy `docker-compose` binary)

This stack is **heavy**. Alongside the app it runs a full Temporal cluster: the Temporal server, its own PostgreSQL, and an Elasticsearch visibility store (its JVM heap is pinned to roughly 256 MB in the compose file). A small VPS can OOM during startup. Plan for a **multi-GB host** (about **4 GB of RAM or more** recommended) with a few GB of free disk for the named volumes.

---

## 🚀 Quick start

All configuration lives **inline in `docker-compose.yaml`**. There is **no `.env.example` to copy**: you edit the `environment:` blocks directly, then bring the stack up.

```bash
git clone https://github.com/GkhanKINAY/postqueen-docker-compose
cd postqueen-docker-compose

# Open docker-compose.yaml and, before your first run, set:
#   1. JWT_SECRET      : replace the placeholder with a long, unique random string
#   2. your public URLs: MAIN_URL, FRONTEND_URL, NEXT_PUBLIC_BACKEND_URL
#                        (only needed if you expose the app beyond localhost)

docker compose up -d
```

<p align="center">
  <img src=".github/assets/compose-up.svg" width="620" alt="docker compose up: the PostQueen stack starts and is ready on localhost 4007" />
</p>

The first run takes a couple of minutes while Temporal initializes. Once the containers are healthy, open the app at:

```
http://localhost:4007
```

**Before your first run**

The shipped `docker-compose.yaml` contains **placeholder secrets** meant for local testing only. Change these before exposing the app to anyone:

- **`JWT_SECRET`** ships as a literal placeholder (`random string that is unique to every install...`). Replace it with your own long, random string. Leaving the placeholder in place is a security hole: anyone could forge session tokens.
- **Database password** defaults to `postqueen-password`. Change it in the `postqueen-postgres` service **and** in the matching `DATABASE_URL` on the app service so the two stay in sync.

> ⚠️ There is no TLS here: the stack serves plain HTTP on `localhost:4007`. That is fine for trying things out, but before you expose the app or connect real social accounts, read [Going to production](#-going-to-production-https-and-oauth) below.

---

## 🔧 Required environment

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

You can supply the variables in a few ways: inline in the `environment:` blocks (how the file ships), via an env file such as `postqueen.env` mounted into `/config` on the app container, or through a `.env` file next to `docker-compose.yaml` (least recommended). The full list of every supported variable (social connectors, storage, Stripe, OAuth, short-link services, and more) lives in the [configuration reference](https://docs.postqueen.ai/configuration/reference).

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

---

## 🌐 Going to production (HTTPS and OAuth)

The compose stack serves plain HTTP on `localhost:4007`. To connect real social accounts you need a public HTTPS domain behind a reverse proxy, because the networks send their OAuth callbacks there. Three steps take you from local toy to production instance:

1. **Put a reverse proxy in front of port `4007`** and let it terminate TLS. Step-by-step guides: [Caddy](https://docs.postqueen.ai/reverse-proxies/caddy), [nginx](https://docs.postqueen.ai/reverse-proxies/nginx), [Traefik](https://docs.postqueen.ai/reverse-proxies/traefik).
2. **Point the URL variables at your domain.** Set `MAIN_URL`, `FRONTEND_URL` and `NEXT_PUBLIC_BACKEND_URL` (with `/api` appended) to the public HTTPS address, then recreate the app container.
3. **Create your OAuth apps.** On self-host, each social network needs its own OAuth app with your domain in its callback URL. Start with the [OAuth configuration guide](https://docs.postqueen.ai/configuration/oauth), then follow the per-network walkthroughs in the [providers overview](https://docs.postqueen.ai/providers/overview).

---

## 💾 Data and backups

Application state is kept in named Docker volumes, most importantly:

- `postgres-volume`: the application database
- `postqueen-uploads`: locally stored media (when `STORAGE_PROVIDER=local`)
- `postqueen-config`: app configuration

Back these up (for example with `docker run --rm -v postgres-volume:/data ...`) before upgrades or migrations. Removing them with `docker compose down -v` deletes all your data. For a complete backup also include `temporal-postgres-data` (it holds in-flight scheduled posts). The `postqueen-redis-data` and `temporal-elasticsearch-data` volumes are caches and indexes that can be recreated.

---

## ⬆️ Upgrading

Pull the latest image and recreate the app container:

```bash
docker compose pull
docker compose up -d
```

Review the [migration guide](https://docs.postqueen.ai/installation/migration) before major upgrades in case migration steps are required.

---

## 🩺 Troubleshooting

- **Stack will not boot, containers OOM, blank screen or login loop:** [self-host troubleshooting](https://docs.postqueen.ai/troubleshooting/self-host)
- **A social network refuses to connect:** [OAuth connection issues](https://docs.postqueen.ai/troubleshooting/oauth-connect)
- **Anything else:** start at the [troubleshooting overview](https://docs.postqueen.ai/troubleshooting/overview)

---

## ☸️ Kubernetes instead?

If your infrastructure runs on Kubernetes, skip Compose and use the official Helm chart: [postqueen-helmchart](https://github.com/GkhanKINAY/postqueen-helmchart) packages the same stack (app, PostgreSQL, Redis, Temporal) with values-driven configuration. The [Kubernetes installation guide](https://docs.postqueen.ai/installation/kubernetes-helm) walks you through it.

---

## ☁️ Cloud, the fast lane

Skip the setup entirely. Create an account, connect your channels, and schedule your first post today: **7-day free trial**, nothing to install, nothing to run.

<p align="center">
  <a href="https://postqueen.ai"><img src=".github/assets/cta-cloud.svg" height="52" alt="Start free for 7 days" /></a>
</p>

<br/>

---

## 🦞 Meet her open agents: OpenClaw &amp; Hermes

The two open-source agents everyone is running right now both speak PostQueen natively. **OpenClaw** lives on your machine and answers you from any chat app. **Hermes** does that too — and give it one brief, it plans your whole week on its own. Both drive the same `postqueen` CLI.

<p align="center">
  <img src=".github/assets/open-agents.svg" width="660" alt="OpenClaw and Hermes running PostQueen: chat apps feed OpenClaw, a one-line brief feeds Hermes, both drive the postqueen CLI and posts land on the calendar" />
</p>

<a href="https://postqueen.ai/openclaw"><img src=".github/assets/spotlight-openclaw.svg" width="410" alt="OpenClaw: runs on your machine; message her from WhatsApp, Telegram, Slack or Discord — set-up guide" /></a> <a href="https://postqueen.ai/hermes-agent"><img src=".github/assets/spotlight-hermes.svg" width="410" alt="Hermes: the self-improving autonomous agent; one brief becomes a planned, verified week — set-up guide" /></a>

**Any other agent works too** — anything that can run a CLI command or call MCP can run your socials. [Agent guide »](https://postqueen.ai/agent)

<br/>

---

## 🌐 Publish everywhere

Write once, be everywhere. PostQueen publishes to **30+ networks** out of the box:

<p align="center">
  <img src=".github/assets/channels/instagram.svg" height="44" alt="Instagram" /> <img src=".github/assets/channels/youtube.svg" height="44" alt="YouTube" /> <img src=".github/assets/channels/google-business.svg" height="44" alt="Google Business Profile" /> <img src=".github/assets/channels/dribbble.svg" height="44" alt="Dribbble" /> <img src=".github/assets/channels/linkedin.svg" height="44" alt="LinkedIn" /> <img src=".github/assets/channels/reddit.svg" height="44" alt="Reddit" /> <img src=".github/assets/channels/tiktok.svg" height="44" alt="TikTok" /> <img src=".github/assets/channels/facebook.svg" height="44" alt="Facebook" /> <img src=".github/assets/channels/pinterest.svg" height="44" alt="Pinterest" /> <img src=".github/assets/channels/threads.svg" height="44" alt="Threads" /> <img src=".github/assets/channels/x.svg" height="44" alt="X" /> <img src=".github/assets/channels/slack.svg" height="44" alt="Slack" /> <img src=".github/assets/channels/discord.svg" height="44" alt="Discord" /> <img src=".github/assets/channels/mastodon.svg" height="44" alt="Mastodon" /> <img src=".github/assets/channels/bluesky.svg" height="44" alt="Bluesky" /> <img src=".github/assets/channels/lemmy.svg" height="44" alt="Lemmy" /> <img src=".github/assets/channels/warpcast.svg" height="44" alt="Farcaster" /> <img src=".github/assets/channels/telegram.svg" height="44" alt="Telegram" /> <img src=".github/assets/channels/nostr.svg" height="44" alt="Nostr" /> <img src=".github/assets/channels/vk.svg" height="44" alt="VK" /> <img src=".github/assets/channels/devto.svg" height="44" alt="Dev.to" /> <img src=".github/assets/channels/medium.svg" height="44" alt="Medium" /> <img src=".github/assets/channels/hashnode.svg" height="44" alt="Hashnode" /> <img src=".github/assets/channels/wordpress.svg" height="44" alt="WordPress" /> <img src=".github/assets/channels/whop.svg" height="44" alt="Whop" /> <img src=".github/assets/channels/kick.svg" height="44" alt="Kick" /> <img src=".github/assets/channels/mewe.svg" height="44" alt="MeWe" /> <img src=".github/assets/channels/twitch.svg" height="44" alt="Twitch" /> <img src=".github/assets/channels/listmonk.svg" height="44" alt="Listmonk" /> <img src=".github/assets/channels/skool.svg" height="44" alt="Skool" />
</p>

| Category | Networks |
| --- | --- |
| **Major social** | X, LinkedIn, Instagram, Facebook, TikTok, YouTube, Threads, Pinterest, Reddit, Bluesky |
| **Community and chat** | Discord, Slack, Telegram, Mastodon, Twitch, Kick, MeWe, VK |
| **Publishing and blogs** | WordPress, Medium, Dev.to, Hashnode, Tumblr, Listmonk, Moltbook |
| **Web3 and decentralized** | Nostr, Farcaster, Lemmy |
| **Creator and business** | Google Business Profile, Whop, Skool, Dribbble |

LinkedIn and Instagram each support both personal and page posting. New connectors ship regularly: see the full list with per-network guides at [postqueen.ai/channels](https://postqueen.ai/channels).

<br/>

---

## ❤️ Community and support

- 🐛 **Found a bug or have an idea?** [Open an issue](https://github.com/GkhanKINAY/postqueen-docker-compose/issues).
- 💌 **Need a hand?** Email **support@postqueen.ai**.
- 📚 **Getting started?** The [docs](https://docs.postqueen.ai) walk you through everything.

If PostQueen saves you time, a ⭐ on the repo genuinely helps other people find it.

<br/>

---

## 🙏 Thank you, Postiz

PostQueen is a fork of [Postiz](https://github.com/gitroomhq/postiz-app) by Nevo David, released under AGPL-3.0. Postiz gave us a rock-solid open-source scheduler: the connectors, the calendar, the Temporal pipeline, years of careful work that we did not have to redo. We forked it because we wanted to take that foundation in a specific direction, a social media manager you talk to instead of operate, and building on Postiz let us start from something that already worked.

Thank you, Nevo David and every Postiz contributor. This project exists because you chose to open-source yours. If PostQueen is not quite what you need, [Postiz](https://postiz.com) itself might be, and it deserves your star too. 🙏

<br/>

---

## 👑 The PostQueen ecosystem

| Repository | What lives there |
| --- | --- |
| [postqueen-app](https://github.com/GkhanKINAY/postqueen-app) | The application itself: frontend, backend, workers |
| [postqueen-agent](https://github.com/GkhanKINAY/postqueen-agent) | Agent CLI and skill: give any AI assistant hands |
| [postqueen-docker-compose](https://github.com/GkhanKINAY/postqueen-docker-compose) | Self-host the whole stack with one command |
| [postqueen-helmchart](https://github.com/GkhanKINAY/postqueen-helmchart) | Run it on Kubernetes |
| [postqueen-n8n](https://github.com/GkhanKINAY/postqueen-n8n) | The n8n community node for no-code automation |
| [postqueen-docs](https://github.com/GkhanKINAY/postqueen-docs) | Source of [docs.postqueen.ai](https://docs.postqueen.ai) |

On npm: [`postqueen`](https://www.npmjs.com/package/postqueen) (CLI) · [`@postqueen/node`](https://www.npmjs.com/package/@postqueen/node) (SDK) · [`n8n-nodes-postqueen`](https://www.npmjs.com/package/n8n-nodes-postqueen) (n8n)

<br/>

<p align="center">
  <strong>Long live the queen.</strong> 👑
</p>

<p align="center">
  <a href="https://postqueen.ai"><img src=".github/assets/cta-cloud.svg" height="52" alt="Start free for 7 days" /></a>
  &nbsp;&nbsp;
  <a href="#-quick-start"><img src=".github/assets/cta-selfhost.svg" height="52" alt="Self-host it free" /></a>
</p>

## License

This repository's source code is available under the [AGPL-3.0 license](LICENSE). Original work © Nevo David / Gitroom and the Postiz contributors. Modifications © PostQueen.
