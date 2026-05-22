The group is starting their build. Your job is to help them create a structured build plan and save it as `PLAN.md` in the project root. Also create a fresh `DECISIONS.md` if one doesn't exist.

## Step 1 - Gather what you need

Before writing any files, ask the group (or infer from the conversation) the following. Ask them as a single grouped question, not one at a time:

1. What is the app called? (Even a working title is fine)
2. What is the one-liner? ("This app lets [user] [do thing] without [pain]")
3. What are the 2-3 must-have things it needs to do? (These become Phase 1 tasks)
4. What are the nice-to-haves if time allows? (These become Phase 2 tasks)

If any of these are already clear from the conversation, don't ask - just use what you know.

## Step 2 - Break into tasks

For each must-have feature, break it into 2-4 concrete build steps. Each task should be something Claude Code can actually do: "build the input form", "write the logic that processes the input", "style the results view". Not "make it good" - real, specific steps.

## Step 3 - Write PLAN.md

Write the complete file to `PLAN.md`:

```markdown
# [App Name] - Build Plan

**One-liner:** [one sentence describing the app]
**Current phase:** Phase 1
**Session started:** [today's date]

---

## Phase 1: Core MVP
*Goal: A working version of the must-have features - demoable, even if rough*
*Target: Complete by ~50 minutes in*

- [ ] [task]
- [ ] [task]
- [ ] [task]
- [ ] [task]

## Phase 2: Polish & Nice-to-Haves
*Goal: Improve the UI, add secondary features, handle edge cases*
*Target: Complete by ~70 minutes in*

- [ ] [task]
- [ ] [task]
- [ ] [task]

## Phase 3: Demo Prep
*Goal: Ready to present to the room*
*Target: Complete by 75 minutes in*

- [ ] Run through the full demo scenario end-to-end
- [ ] Fix any rough edges found during the run-through
- [ ] Run /present to generate the presentation HTML
- [ ] Open presentation.html and check it looks right

---

## User & Context
**Primary user:** [name and role]
**Key scenario:** [the specific moment/situation the user is in when they use this app]

---
*Plan created: [date] | Last updated: [date]*
```

## Step 4 - Create DECISIONS.md (if it doesn't exist)

```markdown
# Decision & Change Log

This file tracks the key decisions made during the build - what we chose, why, and what we ruled out.

---
```

## Step 5 - Copy the starter template

Copy `starter.html` to `index.html` in the project root if `index.html` doesn't already exist. This gives the group a working design-system-styled page to build on immediately. Tell the group to open `index.html` in their browser now so they can see changes as they build.

## Step 6 - Confirm and orient

After writing the files, output a short message to the group:

- Confirm PLAN.md and DECISIONS.md have been created
- State the current phase and what the first task is
- Suggest the opening build prompt they should give Claude: something specific enough to start immediately
- Remind them of the commands they'll need: `/handover` to close a chat cleanly, `/pickup` to resume in a new one, and `/present` at demo time to generate the slide deck
