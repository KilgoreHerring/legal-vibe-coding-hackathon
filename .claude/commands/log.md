The user wants to log a decision or change. Add a new entry to `DECISIONS.md` in the project root (create the file if it doesn't exist).

## If DECISIONS.md doesn't exist yet, create it with this header first:

```
# Decision & Change Log

This file tracks the key decisions made during the build - what we chose, why, and what we ruled out.
It's a record of our thinking, not just our code.

---
```

## Then append a new entry in this format:

```
## [Short decision title] - [HH:MM]

**What we decided:** [One clear sentence describing the decision or change made]

**Why:** [The reasoning - what problem this solves, what constraint drove it, or what the group agreed]

**What we ruled out:** [Alternatives considered and why they were set aside - even if briefly]

**Impact:** [What this changes about the build - a screen, a feature, the data model, the scope]

---
```

## Instructions:
- Infer the decision title and content from what the user has told you and the current conversation context
- If the user has given you specific text, use it - don't paraphrase
- Keep each field concise: 1-3 sentences max
- The time should reflect the approximate current time in the session (if unknown, omit it)
- After writing the entry, confirm to the user: "Logged to DECISIONS.md - [one-line summary of what was logged]"
- Do not show the full file contents back - just confirm the entry was added
