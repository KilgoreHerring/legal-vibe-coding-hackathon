The group is closing this chat session. Your job is to save the current state so the next session can pick up seamlessly with a fresh context.

Do three things in order:

---

## 1 - Update PLAN.md

Read the current `PLAN.md`. Based on everything in this conversation:
- Mark completed tasks with `[x]`
- Mark any task currently in progress with `[~]` (in progress)
- Leave remaining tasks as `[ ]`
- Update the `Current phase` field if the phase has changed
- Update the `Last updated` date at the bottom

Do not change the structure or wording of tasks - only update the status markers and the metadata fields.

---

## 2 - Write HANDOVER.md

Write (or overwrite) `HANDOVER.md` with a precise snapshot of where things stand right now. This file will be read by Claude at the start of the next session - write it for Claude, not for the humans. Be specific and technical where it helps.

```markdown
# Session Handover

**Date:** [today's date]
**Phase:** [current phase]
**Overall progress:** [e.g. "Phase 1 - 3 of 5 tasks complete"]

---

## What was completed this session
[Bullet list of tasks finished - be specific, not vague. "Built the input form with name, matter number, and date fields" not "worked on the form"]

## What is currently in progress
**[Task name]:** [Precise state. Where did this get to? What's been done, what's left? If there's a file and approximate location in the code that's relevant, mention it.]

## Known issues or blockers
[Any bugs, errors, or problems that were encountered and not yet resolved. Include error messages if relevant. "None" if clean.]

## Exact next steps for the next session
1. [First thing to do - specific enough that Claude can start without asking questions]
2. [Second thing]
3. [Third thing if relevant]

## Context that isn't obvious from the code
[Anything a fresh Claude reading the files would miss: verbal decisions, things that were tried and abandoned, constraints the group mentioned, preferences about style or approach]

## Key files
[List the main files in the project and one-line description of what each does - helps Claude orient quickly in a fresh context]
```

---

## 3 - Confirm to the group

After writing both files, tell the group:
- What was marked complete
- What's in progress and where it got to
- Exactly what to do at the start of the next session: "Open a new chat, type `/pickup`, and Claude will restore the full context."

Keep this confirmation short - 4-6 bullet points.
