# Using APIs in Your Build

Two kinds of API are in play during a session: the **AI providers** the kit expects you to wire keys into, and **any other service** a group wants to pull in (a legal-content API, an internal data source, a public dataset). This doc covers both.

> **Never commit keys or tokens.** Put them in `.env` at the project root (gitignored - see `.env.example` for the shape). Ask Claude to read them from there. Don't paste a token into your HTML, into chat, or onto a screen you might share later.

---

## AI providers (the default option)

If a group wants their app to "use AI" - summarise, draft, classify, answer questions - pick one of the three providers below. Any of them works for text. Default to the small/fast tier; it's cheap, quick, and good enough for a demo.

| Provider | Suggested default model | Env vars |
|---|---|---|
| Anthropic (Claude) | `claude-haiku-4-5` | `ANTHROPIC_API_KEY`, `ANTHROPIC_MODEL` |
| OpenAI | `gpt-5-mini` (or `gpt-4o-mini`) | `OPENAI_API_KEY`, `OPENAI_MODEL` |
| Google Gemini | `gemini-2.5-flash` | `GEMINI_API_KEY`, `GEMINI_MODEL` |

Fill these into `.env` before the session (copy `.env.example`). For a single-file browser demo the simplest pattern is a key-entry box in the UI, or have Claude inline the key from `.env`. For anything more substantial, load the key server-side behind a tiny proxy (see below) so it never reaches the page.

---

## Bring your own API

The harness doesn't care what else you plug in. If a group has access to a useful service - a legal knowledge/Q&A API, a company-data API, a public dataset, an internal endpoint - it can be wired in exactly the same way as the AI providers: put credentials in `.env`, and either call the service through a small proxy or inline the values at build time.

A good example is a **legal-content API** such as [FromCounsel](https://www.fromcounsel.com/) - structured UK legal Q&As, legislation, precedents, and corporate deal data. If you have credentials for something like that, point your app at it instead of inventing fake legal content. The same goes for any other API your firm or team can grant access to for the day. Add the relevant `*_BASE_URL` and `*_TOKEN` lines to `.env`, tell the facilitator, and build on top of it.

If you don't have an external service to hand, the bundled `mockdata/` folder gives you realistic fake firm data to build against - see [MOCK_DATA.md](MOCK_DATA.md).

---

## The two wiring patterns

### Pattern A - tiny Node proxy (recommended; keeps the token off the page)

Ask Claude to scaffold a one-file proxy:

> "Add a tiny Node proxy in `server.js` that loads `MY_API_BASE_URL` and `MY_API_TOKEN` from `.env`, listens on `localhost:3000`, and forwards any `/api/*` request to the external API with the Authorization header attached. Serve `index.html` from the same port."

Then in your HTML:

```html
<script>
  async function api(path) {
    const res = await fetch(`/api${path}`);
    if (!res.ok) throw new Error(`API ${res.status}`);
    return res.json();
  }
</script>
```

No token in the page, and CORS is solved as a side effect.

### Pattern B - direct from the browser (fastest to get going)

If you just want to demo and don't mind the token living in the page for the session, ask Claude to **read `.env` and inline the values** when it wires up the call. The token then lives in one place (`.env`) and Claude pastes it in:

```html
<script>
  const API_BASE = "...";  // inlined by Claude from the .env base URL
  const API_TOKEN = "..."; // inlined by Claude from the .env token

  async function api(path) {
    const res = await fetch(`${API_BASE}${path}`, {
      headers: { Authorization: `Bearer ${API_TOKEN}` }
    });
    if (!res.ok) throw new Error(`API ${res.status}`);
    return res.json();
  }
</script>
```

**CORS heads-up for Pattern B.** If you opened `index.html` straight from disk (`file://`) and the browser blocks the call, run a tiny local server instead:

```bash
npx serve .
# or
python -m http.server 8000
```

Then open `http://localhost:8000/index.html`.

---

## Tips for using an external API in a 90-minute build

- **Call the list/index endpoint once, on page load**, into a `const`. Don't refetch.
- **Cache one or two interesting responses to disk** as JSON in `materials/` and have Claude read from there if you keep hitting the same endpoint.
- **Don't try to render every field.** Pull the few you need for the demo and ignore the rest.
- **Strip or ignore heavy markup** (HTML inside responses) for a first pass - the plain text usually reads fine.
- **Pick one slice and go narrow.** One content type, one area, one screen.
