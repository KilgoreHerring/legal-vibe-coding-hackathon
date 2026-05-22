# Run Sheet - The Day

Organiser-and-facilitator choreography for the whole session, across all groups running in parallel. This sits above [FACILITATOR_GUIDE.md](FACILITATOR_GUIDE.md), which covers running a single table. Read both.

**Shape (working plan, may change):** about 90 minutes total - a 10-minute opening from the hosts, a 60-minute build session run in parallel by all groups (4-5 trainees and one Innovation Team facilitator per table), then a 20-minute present-back from three to five groups.

This is the compressed format. If the timetable opens up, the build session can stretch to 90 minutes with a proper plenary showcase at the end - the per-table flow in the kit ([FACILITATOR_GUIDE.md](FACILITATOR_GUIDE.md), [SCENE_SETTER.md](SCENE_SETTER.md)) is written for that longer version. The notes below assume the 90-minute-total version.

*Replace the sample offsets with real times before you print anything.*

---

## Before the day

| Owner | Item |
|---|---|
| Organiser | Confirm the room: seats everyone for the opening and the present-back, with table space for the groups. Screen and clicker. |
| Organiser | Confirm headcount and build the group list - 4-5 trainees per group, one facilitator each. Names on tables. |
| Organiser | Brief the hosts on the 10-minute opening (see "The opening" below). Keep it to 10. |
| Organiser | Decide which groups present back, or how they're chosen - volunteers, facilitator nomination, or organiser's pick during the build. Tell facilitators so they can prime a group that's going well. With only ~20 minutes, it's three to five groups, not all of them. |
| Organiser | Decide the **live-AI question** and tell facilitators: do the prototypes call a real model (API key available on the machines) or are AI features mocked for the demo? Default to mocked unless someone has set up keys. Note it in each table's `CLAUDE.md` if needed. |
| Tech setup | On each machine: install Claude Code, sign in, clone or copy a fresh copy of this repo per group, confirm `CLAUDE.md` loads on open. If running a scenario, drop the source documents into `materials/` in each copy. |
| Tech setup | Test one machine end to end: open in Claude Code, run `/kickoff`, confirm `index.html` renders, run `/present`, confirm `presentation.html` opens in the browser. |
| Organiser | Print: [DAY_PLAN.md](DAY_PLAN.md) for every trainee, [FACILITATOR_GUIDE.md](FACILITATOR_GUIDE.md) and this run sheet for every facilitator. Optional: [SCENE_SETTER.md](SCENE_SETTER.md) sent round in advance. |
| Organiser | Brief facilitators (15 min, ideally the day before): the guide-not-builder role, the compressed time markers below, what to cut, the present-back selection, and the live-AI decision. |

---

## Running order (about 90 minutes)

| Offset | Slot | Who runs it | Notes |
|---|---|---|---|
| 0:00 | Opening (10 min) | the hosts | See "The opening". Hard stop at 10 minutes - the build session needs its full hour. |
| 0:10 | **Build session - 60 min** | Facilitators, per table | See the per-table flow below and [FACILITATOR_GUIDE.md](FACILITATOR_GUIDE.md). Organiser floats, watches the clock, calls 30-minutes-left, 10-minutes-left, and 2-minutes-left across the room. |
| 1:10 | Present-back (20 min) | Organiser / a host | Three to five groups, ~4 minutes each including swap. See "The present-back". |
| 1:30 | Close | The hosts / organiser | One or two lines: what happens to the ideas now (route through the Innovation Team - see [TAKE_BACK_TO_YOUR_TEAM.md](TAKE_BACK_TO_YOUR_TEAM.md)), thanks, done. Fold this into the present-back slot if time is tight. |

---

## The opening (the hosts, 10 minutes)

Slides: [OPENING_DECK.html](OPENING_DECK.html) - open in a browser, full screen, click or arrow-key to advance. Nine slides, roughly a minute each.

What it lands, in order: why you're here (not to become developers - the art of the possible) - what vibe coding is - the shift (idea to working version in an afternoon, not months) - why we're starting with trainees (closest to the friction, whole career ahead) - more practice of law, less of the operational drag around it - what makes a good idea (real, specific, contained) and the four themes - how the next 80 minutes work - close ("what's the most annoying thing I do repeatedly that a computer should be doing?").

No live demo in the opening - there's no time and the groups are about to do it themselves. Hard stop at 10 minutes.

---

## Inside the 60-minute build session

Per-table flow. Tighter than the standalone session flow in the kit - everything is compressed and there's no separate rehearsal block, so the demo gets locked inside the last ten minutes.

| Offset | Phase | Facilitator focus |
|---|---|---|
| 0-10 min | Discovery ([DISCOVERY.md](DISCOVERY.md)) | Push hard for specificity, fast. Still debating at 10 min? Pick one and move - no exceptions. Groups arriving with a clear idea skip this entirely. |
| 10-15 min | Design brief ([DESIGN_BRIEF.md](DESIGN_BRIEF.md)) + `/kickoff` | One user story, one screen. Cut everything else to nice-to-have. Run `/kickoff`. |
| 15-50 min | Build | Stay out of the way unless they're stuck. If stuck, help them write a better prompt - don't take the keyboard. |
| 50-60 min | Polish, `/present`, lock the demo | Hard stop on new features at 50. Tighten the UI, run `/present`, open `presentation.html`, pick the scenario you'd show and decide who says what - even if you're not sure you'll be picked. |

Behind schedule: cut features, not the demo prep. A simple thing that works beats an ambitious thing that doesn't - more so in an hour. Ahead: polish the UI, sharpen the story. No new features after minute 50.

The [SHIPPING_CHECKLIST.md](SHIPPING_CHECKLIST.md) conversation doesn't fit in 60 minutes - point groups at [TAKE_BACK_TO_YOUR_TEAM.md](TAKE_BACK_TO_YOUR_TEAM.md) and [SHIPPING_EXAMPLE.md](SHIPPING_EXAMPLE.md) to read afterwards instead.

---

## The present-back (20 minutes, 3-5 groups)

Not everyone presents. Pick the groups during the build - ones with a working demo and a clear story. Tell those facilitators around the 45-minute mark so they steer the last fifteen minutes towards a tight pitch.

Per group, ~4 minutes including getting set up at the screen:
- Problem - 30 sec
- What they built + live demo - 2.5 min (the demo is the point)
- What it would take to ship, and the ask - 1 min

The host runs a visible countdown and cuts at 4 minutes. The energy depends on holding the line. From their own machine: `presentation.html` plus a live demo of `index.html`. No judging or prizes - this is a learning session, not a competition - unless the organiser has decided otherwise.

If you have a spare two minutes at the end, a host closes with the "what happens to these ideas now" line. If not, the organiser sends it round by email afterwards.

---

## What "done" looks like

By 1:10 every group should have an `index.html` that runs and does something, and a `presentation.html` that opens - whether or not they present. By 1:30 every trainee should leave understanding that they can spot a real problem, describe it well enough for an AI to build something, get to a prototype in under an hour, and that taking it further means a different set of conversations - IT, risk, data, a sponsor. The code is the proof of concept. That mental model shift is the point.

---

## Common failure modes and the fix

| Symptom | Fix |
|---|---|
| Group still arguing about the idea at minute 10 | Facilitator picks one from [USE_CASES.md](USE_CASES.md). A well-executed simple idea beats a brilliant one they never start - and in an hour you cannot afford twenty minutes of debate. |
| Over-scoping | Point at the MVP table in the design brief. "If you only built the first user story, would that be demoable?" Usually yes. Cut the rest. |
| Claude wedges the app and won't recover | Revert the last change (git checkout the file, or ask Claude to undo the last edit) and try a different prompt. 5 minutes max in the compressed format, then move on with what works. |
| AI feature won't work live | Fall back to the mocked version. Decide this at the table, not on stage. |
| Group ahead and bored | UI polish, sharpen the demo story. No new features after minute 50. |
| Opening overruns | Organiser steps in at 10 minutes. The build hour is non-negotiable; the opening is not. |
| Running late overall | Protect the build hour and at least three present-backs. Drop the close to an email. |
