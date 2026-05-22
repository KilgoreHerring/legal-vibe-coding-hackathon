The group is starting a new chat session and needs full context restored. Read the project state files and brief yourself completely before doing anything else.

## Step 1 - Read all state files

Read each of these files if they exist:
- `PLAN.md` - the overall build plan and task status
- `HANDOVER.md` - the snapshot from the end of the last session
- `DECISIONS.md` - the log of decisions made so far

Also do a quick scan of the project directory to understand what files have been built.

## Step 2 - Output a context brief

Present a structured brief to the group so everyone is aligned before building starts. Format it like this:

---

**[App name] - Session [N] Pickup**

**Where we are:** [One sentence on overall progress - phase, % complete, time pressure if relevant]

**What we finished last session:**
- [item]
- [item]

**What's in progress right now:**
[Description of the in-progress task and exactly where it got to - specific enough to continue immediately]

**Known issues to deal with first:**
[Any blockers or bugs from last session. "None" if clean.]

**Up next (in order):**
1. [Next task - specific]
2. [Task after that]
3. [Task after that]

**Key decisions already made:**
[2-4 bullet points summarising the most important choices from DECISIONS.md - things that affect how we build from here]

**Suggested first prompt:**
> [Write the exact prompt the group should paste to continue building - specific, actionable, picks up exactly where they left off]

---

## Step 3 - Wait for the group to confirm

After presenting the brief, ask: "Does this match where you thought you were? Anything to correct before we continue?"

Only start building once the group confirms or corrects. If they say "yes let's go" or similar, proceed with the suggested first prompt immediately.
