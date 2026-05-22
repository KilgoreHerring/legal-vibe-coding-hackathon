# Trainee Litigation Simulator — Build Plan

**One-liner:** This app lets trainee solicitors practise drafting real litigation documents and get instant AI-powered feedback — without needing to wait for a partner to review their first draft.
**Current phase:** Phase 3
**Session started:** 2026-05-05

---

## The Scenario

The exercise is based on **Fairway Events Ltd v Luxe Marquees Ltd** — a realistic pre-action dispute where the trainee must draft a Letter Before Action (for the other side) and a Client Advice Note (privileged). The content, documents and rubric are all pre-loaded. The core challenge being tested is whether the trainee understands the distinction between what goes in correspondence (firm assertion, no strategy) versus privileged advice (candid, honest about weaknesses).

---

## Phase 1: Core MVP
*Goal: A working, demoable app — trainee can review docs, draft both tasks, and get AI feedback*
*Target: Complete by ~50 minutes in*

- [x] Build the app shell — full-screen split layout with design-system-styled header, step tabs (1. Review / 2. Draft LBA / 3. Advice Note), left doc panel + right task panel
- [x] Build the document viewer — 3 tabs (Client Email, Barker & Co LBA, The Contract) with full formatted content of all three case documents
- [x] Build Step 1 (Review Documents) — reading checklist with 3 items, key issues summary cards, "proceed to Step 2" button
- [x] Build Step 2 (Draft LBA) — requirements list, large draft textarea with word count, API key modal, submit button, Claude grading with full LBA rubric (45pts), feedback display with score + annotations + strengths + improvements
- [x] Build Step 3 (Draft Advice Note) — same pattern as Step 2 with advice note requirements and rubric (40pts), complete/revise flow

---

## Phase 2: Polish & Nice-to-Haves
*Goal: Improve the experience, add secondary features*
*Target: Complete by ~70 minutes in*

- [x] Add "Ask Catherine Osei" floating chat panel — AI persona as supervising partner, Socratic guidance style *(note: requires API key — flag as deployment consideration for real day)*
- [x] Add revise & resubmit flow — hide grading panel, re-enable editing, re-submit for improved score
- [x] Add overall score tracker in the header — running total of LBA + Advice Note scores out of 85
- [x] Tighten the document viewer — highlight key clauses with coloured tags (Clause 2.2, 5.1, 6.1), add Schedule 1 equipment table

---

## Phase 3: Demo Prep
*Goal: Ready to present*
*Target: Complete by 75 minutes in*

- [ ] Run through the full demo scenario end-to-end
- [ ] Fix any rough edges found during the run-through
- [x] Run `/present` to generate the presentation HTML
- [x] Open `presentation.html` and check it looks right

---

## User & Context

**Primary user:** Trainee solicitor in a Disputes seat (no prior knowledge of this specific matter)
**Key scenario:** The trainee has just received a client email forwarded by their supervising partner. They have to read three documents, then independently produce a formal LBA and a privileged advice note — the same task they'd face on a real seat rotation.

---

## Content Already Available

All exercise content is ready to embed in the app:
- Full client instruction email (Rebecca Haines / Fairway Events)
- Full Barker & Co LBA (N. Walker / Luxe Marquees)
- Full contract with Schedule 1
- Detailed grading rubric for both tasks (in `exercise/OVERVIEW.md` — created during planning)
- Task instructions for LBA (45pts) and Advice Note (40pts)

---

## API / Technical Notes

- Single HTML file (no server, no build step)
- Claude API called directly from browser — API key entered via modal on first use, stored in `sessionStorage`
- Model: `claude-sonnet-4-6`
- Grading returns structured JSON: score, grade, annotations, strengths, improvements, critical errors
- **Deployment question for real day:** trainees won't have their own API keys — consider a simple proxy or pre-configured key for the conference

---

*Plan created: 2026-05-05 | Last updated: 2026-05-06 | All phases complete*
