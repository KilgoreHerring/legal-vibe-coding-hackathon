# Mock Data

You're building your hackathon app in 90 minutes. You can't talk to Outlook, the firm document management system, the practice management database, or any real client information. So we've baked you a fictional firm to play with.

Pretend it's real. Use it to make your demo land.

---

## What's in the box

`mockdata/` is the folder. Everything in it is invented. Names of clients, matters, employees, dispute counterparties, deal counterparties - **all fictional**. Anchor "today" is **15 May 2026** so dates feel current on the day of the hackathon.

| File | What it is | Records | Good for |
|---|---|---|---|
| `mockdata/people.json` | Firm directory - partners, associates, trainees, paralegal, knowledge lawyer | 25 | "who's who" lookups, mentions, assignment |
| `mockdata/clients.json` | Firm clients across 15 sectors | 15 | Client briefing, conflict checks, BD targeting |
| `mockdata/matters.json` | Live and recently closed matters | 25 | Matter dashboard, time recording, cross-references |
| `mockdata/emails.json` | Inbox for Marcus Holloway (corporate trainee) | 55 | Inbox triage, summarisation, "what should I work on first", ad hoc work prioritisation, draft-feedback assistant |
| `mockdata/calendar.json` | Marcus's calendar - past 2 weeks + next 3 weeks | 40 | Meeting prep, time recording from calendar, conflict detection |
| `mockdata/time-entries.json` | Posted time entries + draft + system-suggested | ~37 | Time recording assistant, narrative writer, missing-time detector |
| `mockdata/tasks.json` | Marcus's personal task list | 25 | Daily brief, prioritiser, deadline tracker |
| `mockdata/precedents.json` | Clause library | 25 | Clause explainer, market-standard checker, drafter |
| `mockdata/deals.json` | Fictional market deal feed | 15 | Deal tracker, client intel, BD prompt |
| `mockdata/news.json` | Fictional regulatory and market news | 15 | Knowledge alerts, "what changed", client briefing |
| `mockdata/documents-index.json` | Catalogue of the documents in `documents/` | 18 | Document picker, search, metadata |
| `mockdata/documents/*.md` | Substantive fake legal documents (NDA, employment, lease, supply, engagement letter, board resolutions, SPA extract, settlement, privacy notice, client instruction, DDQ response, CP checklist, SHA, SaaS subscription, facility agreement, DPA, consultancy agreement, heads of terms) | 18 | Redline summarisers, clause explainers, document Q&A, drafting assistants |

Everything cross-references by ID. A matter has a `client` (clients.json), `partner` (people.json), `feeEarners` (people.json). An email has a `matter` (matters.json) and `from`/`to` (people.json or external addresses). A document has a `matter` and `client`. You can build joins between any of these.

---

## How to use the data

### Default: ask Claude to inline it

The simplest pattern, and the one we recommend, is:

> "Use mockdata/emails.json as the seed inbox. Inline the data into the HTML so it works when I open the file directly."

Claude will read the JSON file, embed the data inside your `index.html` as a `const` (or in a `<script type="application/json">` block), and your code reads from that variable. No fetch, no server, works from `file://`.

This is the **default approach** because trainees opening `index.html` from disk will hit CORS errors with `fetch()`.

```html
<script>
  const EMAILS = [
    { id: "e001", subject: "URGENT: Project Lighthouse...", ... },
    // ... etc.
  ];
</script>
```

### Alternative: fetch with a local server

If your group is comfortable running a local server, `fetch()` works fine:

```html
<script>
  fetch('./mockdata/emails.json')
    .then(r => r.json())
    .then(data => {
      // data._note, data.owner, data.emails
    });
</script>
```

Run from the project root with **any one of**:

```
# Python (almost always available)
python -m http.server 8080

# Node (if available)
npx serve .

# VS Code: install Live Server extension and click "Go Live"
```

Then open `http://localhost:8080/index.html`. Tell Claude "use a local server, fetch from `./mockdata/`."

**Default** is inline. **Use fetch** only if you specifically want it.

---

## Schemas (quick)

Below is the shape of each file. Claude can read the full files when you ask - this is just an at-a-glance reference for facilitators and stuck groups.

### people.json
```json
{ "people": [
  { "id": "p001", "name": "...", "role": "Senior Partner|Partner|Of Counsel|Senior Associate|Associate|Trainee|Paralegal|Knowledge Lawyer",
    "practiceGroup": "Corporate|Employment|Banking & Finance|Disputes|Real Estate|Commercial|IP|Tax|Data Protection",
    "email": "...", "office": "London|Manchester|Leeds", "phone": "...",
    "qualifiedYear": 2005, "currentSeat": "...", "trainingContractStart": "...", "secretary": "p024" }
]}
```

### clients.json
```json
{ "clients": [
  { "id": "c001", "name": "...", "sector": "...", "size": "Listed|Mid-market|Large private|Scale-up|Small business",
    "hq": "...", "relationshipPartner": "p001", "since": "2017-03-14", "notes": "..." }
]}
```

### matters.json
```json
{ "matters": [
  { "id": "m001", "code": "NWI-1042-25", "name": "...", "client": "c001",
    "partner": "p002", "supervisor": "p012", "feeEarners": ["p002", ...],
    "status": "active|completed|on_hold", "practiceGroup": "...", "matterType": "...",
    "openedDate": "2025-11-04", "closedDate": "...", "feesBilled": 412500, "feesWIP": 86200,
    "budget": 650000, "description": "..." }
]}
```

### emails.json
```json
{ "owner": "p018", "emails": [
  { "id": "e001", "threadId": "t-...", "subject": "...", "from": "p002|external@...",
    "to": ["p018"], "cc": ["p012"], "date": "2026-05-14T22:47:00Z",
    "folder": "inbox|sent", "read": true|false, "flagged": true|false,
    "matter": "m001|null", "body": "..." }
]}
```

### calendar.json
```json
{ "owner": "p018", "events": [
  { "id": "ev001", "title": "...", "start": "2026-05-15T09:00:00+01:00", "end": "...",
    "location": "...", "type": "client_meeting|internal_meeting|training|deadline|court_or_hearing|social|bd_event|pro_bono",
    "matter": "m001|null", "attendees": ["p002", "External: ..."], "description": "..." }
]}
```

### time-entries.json
```json
{ "entries": [
  { "id": "te001", "feeEarner": "p018", "matter": "m001|null",
    "date": "2026-05-14", "hours": 4.8, "narrative": "...",
    "status": "posted|draft" }
], "proposed": [
  { ..., "status": "proposed", "source": "calendar:ev013" }
]}
```

### tasks.json
```json
{ "owner": "p018", "tasks": [
  { "id": "tk001", "title": "...", "matter": "m001|null", "assignedBy": "p002|null",
    "dueDate": "2026-05-15T09:00:00+01:00",
    "priority": "high|medium|low", "status": "open|in_progress|blocked|done",
    "description": "..." }
]}
```

### precedents.json
```json
{ "precedents": [
  { "id": "pr001", "title": "...", "category": "NDA|M&A|Shareholder|Employment|Commercial|Real Estate|Banking|IP|Data Protection|Boilerplate",
    "tags": ["...", "..."],
    "slant": "neutral|seller-friendly|buyer-friendly|tenant-friendly|landlord-friendly|employer-friendly|employee-friendly|lender-friendly|...",
    "lastUpdated": "2026-04-22", "body": "..." }
]}
```

### deals.json
```json
{ "asOfDate": "2026-05-15", "deals": [
  { "id": "d001", "date": "2026-05-13", "headline": "...", "type": "...",
    "sector": "...", "value_GBP_m": 140, "buyer": "...", "target": "...",
    "advisors": "...", "source": "...", "summary": "..." }
]}
```

### news.json
```json
{ "asOfDate": "2026-05-15", "news": [
  { "id": "n001", "date": "2026-05-14", "headline": "...", "category": "...",
    "source": "...", "summary": "...",
    "relevant_to_clients": ["c006"], "relevant_to_matters": ["m015"] }
]}
```

### documents-index.json
```json
{ "documents": [
  { "id": "doc001", "file": "documents/mutual-nda.md", "title": "...",
    "type": "NDA|Employment contract|Commercial contract|Lease summary|...",
    "matter": "m001|null", "client": "c001|null",
    "lastModified": "2026-04-18", "wordCountApprox": 950,
    "tags": ["..."] }
]}
```

---

## Use-case mapping

If your group is stuck, here's what the data supports out of the box:

| Idea | What to read |
|---|---|
| **Daily brief** ("what should I do first") | `tasks.json`, `emails.json`, `calendar.json` for today |
| **Inbox triage** | `emails.json` - mix of urgent, junk, supervisor, client, deadline |
| **Time recording assistant** | `calendar.json` past week + `matters.json` + sample `time-entries.json` narratives. Generate suggested narratives for unposted hours |
| **New matter intake / triage** | `documents/client-instruction.md` + `clients.json` + `matters.json` (existing - check for conflicts) |
| **Client briefing pack** | `clients.json` + their `matters.json` + recent `emails.json` for that client + relevant `news.json` |
| **Knowledge / clause search** | `precedents.json` + `documents/` |
| **Clause explainer / market-standard checker** | `precedents.json` (each has a `slant` field) |
| **Redline summariser** | `documents/spa-extract.md` (already has buyer's mark-up overlaid) |
| **CP / completion tracker** | `documents/cp-checklist.md` |
| **Deal announcement tracker / BD prompt** | `deals.json` + match against `clients.json` sectors |
| **Knowledge alert / "what changed"** | `news.json` (each item has `relevant_to_clients` and `relevant_to_matters`) |
| **Conflict checker** | `clients.json` + `matters.json` (filter by client name match) |
| **Witness / chronology builder** | `emails.json` filtered by matter + chronological order |

---

## House rules for the day

- **Anonymity**: every name, email, phone number and registered number is invented. Never replace mock data with real client information for a demo.
- **Anchor date**: assume "today" is **2026-05-15**. Tell Claude this so dates feel current.
- **Don't hallucinate**: if you need data that isn't in mockdata, ask Claude to add it to the file as a small extension - don't invent it inline in your code.
- **Resist the urge to add a backend**: the goal is a 90-minute single-file demo. Keep state in memory or `localStorage`. No databases.
- **Don't ship code with real API keys**: if your group ends up calling Claude or another model from the browser, mock the response or use a key your facilitator provides for the day.

---

## Extending the data

If you want to add to the dataset (more emails, a new document, a new matter):

1. Open the relevant JSON file.
2. Copy an existing entry and modify it - keep the schema the same.
3. Use IDs that follow the existing pattern (`e041`, `m026`, `doc013`).
4. Cross-reference cleanly: if you add a matter, point it at an existing client and partner (or add those too).

You can ask Claude: *"add three more emails to mockdata/emails.json for the Helix Series C thread, escalating in tone, dated 12-14 May."* That works.
