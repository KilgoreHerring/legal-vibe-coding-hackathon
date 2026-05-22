# Design Brief

Once you've completed the discovery questions, spend 5–10 minutes turning your answers into a design brief. It's your group's shared contract before building starts: it stops scope creep, keeps everyone aligned, and makes your prompts to Claude much better.

Work through each step in order. Then run `/kickoff` to create your build plan.

---

## Step 1 - Write Your One-Liner

Complete this sentence before anything else:

> "This app lets **[user]** **[do specific thing]** without **[painful current process]**."

Example: *"This app lets trainees track signature page completion without chasing 12 people over email."*

If you can't finish that sentence clearly, you're not ready to build yet. Keep talking.

---

## Step 2 - Define Your User

Give your user a name and a moment. The more specific, the better.

> **[Name]** is a **[role]** at the firm. It's **[time of day / situation]**. They need to **[task]** but right now they have to **[painful current process]**. They're **[feeling]**. They would love a tool that **[outcome]**.

Example: *"Sarah is a first-seat trainee. It's 6pm on a Friday before a Monday closing. She needs to chase 14 signatories but has to do it manually over email. She's stressed and worried she'll miss someone. She'd love a tool that showed her at a glance who has signed and who hasn't."*

---

## Step 3 - Write 3 User Stories

User stories are the language of product design. Each one defines a piece of real user value.

Format: **"As a [user], I want to [action] so that [benefit]."**

Keep to 3 maximum. These become your build checklist.

| # | User story | Priority |
|---|---|---|
| 1 | As a [user], I want to... so that... | Must have |
| 2 | As a [user], I want to... so that... | Must have |
| 3 | As a [user], I want to... so that... | Nice to have |

---

## Step 4 - Map Your Screens

List every screen or view in your app before Claude builds anything. If you have more than 4 screens, cut some - you have 90 minutes.

| Screen | What the user does here |
|---|---|
| Home / Landing | |
| [Screen 2] | |
| [Screen 3] | |

---

## Step 5 - Set Your MVP Scope

Be ruthless. Anything in "Nice to have" only gets built if the must-haves are done and working.

| Must have (build today) | Nice to have (if time allows) | Out of scope |
|---|---|---|
| | | |

---

## Step 6 - Make Your Key Technical Decisions

Claude will suggest options, but your group should agree on these before the build starts.

- Language / framework: what will the app be built in? Claude will usually suggest HTML/CSS/JS for a simple web app, or Python for something data-heavy.
- Data: does the app need to save anything? If so, how? Browser local storage works for simple apps; a JSON file or lightweight database for anything more.
- Style: should it look like anything in particular? Clean and minimal, firm-branded, like an existing internal tool?
- Hosting: where will it run for the demo? Just locally in the browser is fine for today.

---

Once you've worked through these steps, run `/kickoff` in the chat and Claude will build your `PLAN.md`.
