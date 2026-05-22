# Shipping Inside a Law Firm - A Worked Example

A short reference for the end-of-session conversation: what production actually looks like if a group wants to take a prototype further.

> **This is a worked example, not a template to copy verbatim.** It describes how one mid-to-large UK law firm (anonymised here as **Nairo Partners LLP**) handles the path from prototype to pilot. The shape is realistic and broadly transferable, but the specifics - the exact stack, the data-classification tiers, the names of internal tools and committees - will be different at your firm. Swap them in. The point is to show trainees that "it runs in a browser" and "the firm uses it" are separated by a real, knowable process.

---

## The stack (example)

At Nairo Partners, most internal tools live on top of the same handful of platforms. Yours will look similar in shape even if the names differ.

- **Microsoft 365** is the productivity layer (Outlook, Teams, SharePoint, OneDrive, Word, Excel, PowerPoint)
- **Microsoft Azure** is the primary cloud platform - anything internal that needs hosting most likely lives here
- **Active Directory / Entra ID** handles identity, single sign-on, and access control
- A **document management system** (e.g. iManage, NetDocuments) is the matter and document store
- An **internal generative AI assistant** - a ring-fenced GPT-style deployment inside the firm's environment - covers non-confidential drafting and summarising
- An **approved third-party AI platform** is cleared for legal work on confidential matter content
- **Microsoft 365 Copilot** is rolled out for general productivity tasks

If you're imagining where a prototype would live in production, the realistic answer for most internal tools is **a web app on the firm's cloud, behind firm SSO, with data sitting in a firm-controlled store**.

---

## InfoSec review - the short version

Any new tool, internal or external, goes through an information-security review before it can be deployed. At a high level it covers:

- **Hosting and architecture** - where does the app run, how is it accessed, who can see it?
- **Authentication** - is it behind SSO / Entra ID? Who's authorised?
- **Data flow** - what data goes in, where does it go, does anything leave the firm's environment?
- **Encryption** - in transit and at rest
- **Vendor assessment** - if a third party is involved, ISO 27001 alignment and standard supplier due diligence
- **Logging and monitoring** - who sees what's happening with the tool

The review is run by the firm's IT and information security team. New tools don't get deployed without it.

---

## Data classification - the one question that drives everything

Before any of the above, the most important question is: **what data does the tool handle?**

Most firms run a tiered model. A representative version:

| Tier | What it can handle |
|---|---|
| **Restricted+** | Confidential and Restricted information |
| **Confidential** | Confidential information |
| **Public tools** | General, non-confidential content only |

Public tools include the consumer versions of ChatGPT, Claude, Gemini, and (importantly) **the Claude Code you used today**. That's why this session uses synthetic or anonymised content only.

If your prototype only ever needs general/public content, the path to production is light. If it touches matter data, client documents, or anything privileged, you're into the higher tiers and the conversation is bigger.

---

## The path from prototype to pilot

A rough sketch of what taking an idea further looks like:

1. **Find a sponsor** - a partner or team lead who actually wants the outcome
2. **Bring it to the people who own internal tooling** - at Nairo Partners that's the Innovation Team; at your firm it might be IT, a knowledge or innovation function, or a transformation team
3. **InfoSec and data protection review** - alongside any vendor due diligence if a third party is involved
4. **Scoped pilot** - one team, one matter type, defined success criteria
5. **Review and decide** - scale it, adjust it, or stop

Most prototypes don't need their own bespoke build. Often the right answer is "use an existing approved platform and configure it for this use case" - a much shorter path than building something new.

---

## What this means for your demo

When you present, the "what would it take to ship" slide doesn't need to be a full security plan. A credible answer covers:

- **Where it would run** (a firm-hosted web app behind SSO is the standard answer)
- **What data it touches** (and therefore which classification tier)
- **What would need reviewing** (InfoSec, data protection, vendor terms if relevant)
- **Who would own it** (which team, which sponsor)

Short, honest, and specific beats a polished but vague answer every time.
