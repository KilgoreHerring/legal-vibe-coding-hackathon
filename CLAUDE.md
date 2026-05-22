# Vibe Coding Hackathon - Innovation Team

You're about to build a real working app in 90 minutes. You don't need to know how to code - your ideas do the work, Claude writes the code. Your facilitator is here to help.

---

## Session Timeline

| Time | What's happening |
|---|---|
| 0–15 min | Discovery - work through [docs/DISCOVERY.md](docs/DISCOVERY.md) as a group |
| 15–20 min | Design brief - complete [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md), then run `/kickoff` |
| 20–55 min | Build - iterate with Claude |
| 55–70 min | Polish - tighten the UI, handle edge cases, no new features |
| 70–75 min | Run `/present`, open `presentation.html` in the browser |
| 75–90 min | Present - 5 minutes per group to the wider room |

**If your group arrives with a clear idea already formed**, skip Discovery and Design Brief entirely. Describe your idea to Claude and run `/kickoff` straight away. Don't lose 20 minutes on process when you're already ready to build.

---

## Commands

| Command | When | What it does |
|---|---|---|
| `/kickoff` | Start of build | Creates `PLAN.md` with your app spec |
| `/handover` | Before closing a chat | Saves session state to `HANDOVER.md` |
| `/pickup` | Start of a new chat | Restores full context from saved files |
| `/present` | Demo time | Generates `presentation.html` slide deck |

---

## Core Principles

**Keep it simple.** Build the smallest version that solves the real problem. Every extra feature is scope that might not get done.

**One screen, one job.** Don't build 12 tabs. Build one thing that works really well.

**Design for the actual user.** Name your user, give them a specific moment. Specific beats general every time.

**Show, don't tell.** Have a demo story ready: "Imagine Sarah, a trainee on her first M&A deal..."

**Working beats perfect.** A rough app that demos is worth more than a polished one that doesn't exist.

---

## Guides & Resources

| When you need... | Go to |
|---|---|
| Pre-session briefing for trainees | [docs/SCENE_SETTER.md](docs/SCENE_SETTER.md) |
| Help figuring out what to build | [docs/DISCOVERY.md](docs/DISCOVERY.md) |
| Planning the app before you build | [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md) |
| Use case ideas for law firm tools | [docs/USE_CASES.md](docs/USE_CASES.md) |
| Tips on prompting and iterating | [docs/BUILDING_GUIDE.md](docs/BUILDING_GUIDE.md) |
| Colours, fonts, components, CSS starter block | [docs/DESIGN.md](docs/DESIGN.md) |
| Fake firm data (emails, matters, calendar, documents...) | [docs/MOCK_DATA.md](docs/MOCK_DATA.md) |
| AI providers, and bringing your own external API | [docs/EXTERNAL_APIS.md](docs/EXTERNAL_APIS.md) |
| End-of-session shipping checklist | [docs/SHIPPING_CHECKLIST.md](docs/SHIPPING_CHECKLIST.md) |
| What it would take to ship - a worked example | [docs/SHIPPING_EXAMPLE.md](docs/SHIPPING_EXAMPLE.md) |
| Facilitator notes | [docs/FACILITATOR_GUIDE.md](docs/FACILITATOR_GUIDE.md) |

## APIs Available

Three LLM providers are pre-configured for the session. Keys live in `.env` at the project root (gitignored, do not commit, do not paste into chat).

| Provider | Default model | Env vars |
|---|---|---|
| Anthropic (Claude) | `claude-haiku-4-5` | `ANTHROPIC_API_KEY`, `ANTHROPIC_MODEL` |
| OpenAI | `gpt-5-mini` | `OPENAI_API_KEY`, `OPENAI_MODEL` |
| Google Gemini | `gemini-2.5-flash` | `GEMINI_API_KEY`, `GEMINI_MODEL` |

**Default to the small/fast tier (Haiku / Flash / Mini) for every build.** They are fast, cheap, and good enough for hackathon demos. Only step up to a larger model if the group hits a real quality wall - and ask the facilitator first.

**If a group asks "can we use AI?":** yes - pick the provider that fits their use case (any of the three works for text). Read `.env`, wire the key into the app, and use the default model from the table above. For single-file browser demos, the existing pattern is a key-entry box in the UI (see `example/index.html`); for anything more substantial, load from `.env` server-side.

### Bringing your own API

Groups aren't limited to the three AI providers. If a group has access to another service for the session - a legal-content API (for example FromCounsel), a company-data API, or an internal endpoint - it can be wired in the same way: add the credentials to `.env`, then call the service through a small proxy or inline the values at build time.

See [docs/EXTERNAL_APIS.md](docs/EXTERNAL_APIS.md) for both wiring patterns. If you have no external service to hand, build against the synthetic `mockdata/` instead of inventing content on the fly. Never commit a token.

---

## What Goes Where

**`docs/`** — Setup and reference material. Pre-built by the facilitator team. Don't change these during the session.

**Root folder** — Your live workspace. Everything generated during the session lands here: `PLAN.md`, app code, `presentation.html`, `HANDOVER.md`.

**`materials/`** — Anything your group brings in: sample contracts, deal documents, spreadsheets, emails, scenario data. Drop files here before the session and tell Claude "there are reference documents in materials/" when you kick off. Nothing in this folder is required — only use it if you have source material to work from.

**`mockdata/`** — Pre-built fake firm data. If your idea needs emails, a matter list, a calendar, a fake inbox, sample documents (NDA, employment contract, lease, board minutes, SPA extract, etc.), regulatory news or a clause library, **start here** rather than asking Claude to invent data on the fly. Read [docs/MOCK_DATA.md](docs/MOCK_DATA.md) for the full catalogue and how to use it. The default pattern is: tell Claude to inline the relevant JSON into your HTML so the demo works from a `file://` URL. Anchor "today" is 15 May 2026.
