# Use Case Inspiration

Stuck on what to build? Here are themes and ideas relevant to a trainee's world. Pick one, combine two, or use these to spark your own idea.

The best apps solve a real, specific problem you've actually experienced, not a theoretical one.

---

## The Trainee's Role

What does a trainee actually spend their time on? Can any of it be automated or augmented?

- A **daily brief** that summarises what tasks are on your plate and in what priority order
- A **seat onboarding guide** that explains what a new practice area involves and what you'll be doing
- A **time tracker** that logs what you're working on and helps you write your time narratives at the end of the day

---

## Document Tasks

The repetitive, process-heavy work that takes time but not much judgement.

- **Signature pages**: Generating, organising, or tracking signature pages for a transaction closing
- **Redline summaries**: Turning a tracked-changes document into a plain-English summary of what changed and why it matters
- **CP lists**: Building or updating a conditions precedent checklist and tracking which items are open/closed
- **Execution versions**: Checking that a final execution version matches the agreed redline

---

## Training & Learning

Tools that help trainees learn faster or more independently.

- A **law quiz** that tests knowledge on a specific area relevant to the seat
- A **clause explainer** that takes a piece of legal text and explains it in plain English
- A **"first day on deal" guide** that explains a transaction type, the key parties, and what the trainee's role is
- A **precedent companion** that explains why a clause is drafted a certain way and what it protects against

---

## Relationships & Business Development

Tools that help lawyers stay close to clients and spot opportunities.

- **Client intelligence**: A dashboard that surfaces what deals a client is doing in the market (from public sources)
- An **events matcher** that takes a client's industry/interests and suggests relevant firm events or thought leadership
- A **relationship tracker**: who knows who, when they last met, whether the relationship is warm or cold
- A **deal announcement tracker**: surfaces recent deal announcements in a practice area to help associates stay current

---

## Knowledge & Research

Tools that make the firm's knowledge more accessible.

- A tool that answers **"what does this clause mean?"** questions with guidance tailored to a specific deal type
- A **market standard checker**: given a clause, is this market standard, borrower-friendly, or lender-friendly?
- A **jurisdiction primer**: quick-reference guide to how a deal structure works in a specific jurisdiction
- A **know-your-client brief**: pulls together what the firm knows about a company before a meeting

---

## Using a Real External API (optional)

If a group has access to a real external service - a legal-content API such as FromCounsel, a company-data API, or an internal endpoint - they can build on real data instead of invented examples. See [EXTERNAL_APIS.md](EXTERNAL_APIS.md) for how to wire one in. A legal-content API in particular unlocks ideas like:

- A **plain-English clause explainer** that retrieves a relevant Q&A and has Claude rewrite it for a trainee audience
- A **legal Q&A bot** with proper citations and deep links back to the source
- A **statute lookup** tool - search legislation by keyword, render the section, summarise it
- A **deal feed / market-standard checker** built on real corporate deal data (IPOs, secondary offers, offer prices, fees)
- A **glossary of the day** built from embedded glossary terms
- A **seat-onboarding guide** that surfaces the top Q&As a trainee starting in corporate, employment or R&I should read

No external service to hand? Build against the synthetic `mockdata/` fake firm instead - e.g. an inbox-triage tool that attaches relevant background reading to any email that mentions a legal concept.

---

## If You're Still Stuck

Ask yourself: *"What's the most annoying thing I do repeatedly that a computer should be doing?"*

That's usually the best app idea in the room.
