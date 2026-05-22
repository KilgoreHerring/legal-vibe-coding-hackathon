# Building Guide

Tips for working with Claude during the build. Come back to this if you get stuck or things aren't going the way you expected.

---

## Starting the Build

Give Claude a clear brief. Use this as your opening prompt template:

> "I want to build a web app for [user]. The main thing it does is [core function]. It should have [feature 1], [feature 2], and [feature 3]. Keep it simple - we have 90 minutes. Use a clean, professional design."

The more specific you are, the better the first version will be.

---

## Iterating

- Build the core first, then add. Don't describe everything at once.
- After each change, test it before asking for the next thing.
- If something doesn't look right, describe what you expected vs. what you got.
- Ask Claude to explain anything you don't understand - it won't judge you.

---

## When Things Go Wrong

If Claude produces an error, paste the full error message back and say "please fix this".

If the app doesn't look right, describe what you see vs. what you want. "The button is in the top left but I want it centred at the bottom of the form."

If Claude does something unexpected, say "that's not what I meant" and try again with a clearer description.

If you're properly stuck, ask your facilitator.

---

## Good Prompts vs. Bad Prompts

| Instead of... | Try... |
|---|---|
| "Make it better" | "Make the button bigger and change the colour to dark blue" |
| "Fix the bug" | "When I click submit, nothing happens. I expected the form to save and show a confirmation message." |
| "Add more features" | "Add a way for the user to download the output as a PDF" |
| "Make it look nice" | "Use a clean white background, dark navy text, and a simple card layout" |
| "It's broken" | "When I enter a name with an apostrophe the page goes blank" |

Both columns follow the same logic: describe the specific behaviour you want, or the specific thing that's wrong.

---

## Coding Best Practices

You don't need to know how to code, but these principles will help you produce better results:

- One change per message. Multiple requests at once often produces mixed results.
- Get each feature working before asking for the next one.
- If Claude uses vague names like "button1" or "div3", ask it to use names that describe what they do.
- A rough app that demos is worth more than a polished one that isn't finished.
- If a change breaks something that was working, ask Claude to revert that change and try a different approach.
