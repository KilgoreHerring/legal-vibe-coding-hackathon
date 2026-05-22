Look at everything built in this project - the code, any files, and the conversation context - and generate a complete, self-contained HTML presentation file saved as `presentation.html` in the project root.

The file should be a polished slide deck that can be opened directly in a browser and presented to the room. Build it as follows:

## Design requirements
Use the Nairo Partners design system (docs/DESIGN.md). For slides specifically:
- **Background:** `#1A2E44` (np-deep-navy)
- **Heading text:** `#FFFFFF`
- **Body text:** `#E6E8ED`
- **Primary accent:** `#068FB1` (np-teal) - used for highlights, underlines, active elements
- **Gold callout:** `#F9AD23` (np-gold) - used for key stats or emphasis
- **Decorative gradient:** `linear-gradient(135deg, #A8D4E6 0%, #C4A8D6 40%, #E8A0BF 70%, #068FB1 100%)` - watercolour, used as a subtle background accent at low opacity
- **Font:** `"Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif`
- Full-screen slides, one per section
- Navigate with left/right arrow keys OR clicking anywhere on the slide
- Slide counter (e.g. "3 / 6") in the bottom right in `#666B73`
- App name in the top left of every slide in `#E6E8ED`
- A thin teal gradient bar (`linear-gradient(90deg, #068FB1, #32BEF0)`) at the very top of each slide
- No external dependencies - everything self-contained in one file

## Slides to generate

**Slide 1 - Title**
- App name (large, centred)
- One-sentence tagline describing what it does
- Team members' names
- "[Firm or team name] Hackathon - [date]"

**Slide 2 - The Problem**
- Heading: "The Problem"
- Who the user is and what painful/slow/manual thing they have to do
- How significant it is (time, frequency, frustration)
- Use 2-3 bullet points, each punchy and specific

**Slide 3 - Our Solution**
- Heading: "What We Built"
- One clear sentence at the top saying what the app does
- 3-4 bullet points of the key features that were actually built today
- A short "how it works" note if relevant

**Slide 4 - The Demo**
- Heading: "See It In Action"
- A short narrative scenario: "Meet [persona], a [role] who needs to..."
- 3-4 bullet points walking through the key demo steps
- This slide is a speaker's guide - shown while the live demo runs

**Slide 5 - What It Would Take to Ship**
- Heading: "From Prototype to Production"
- 3 honest bullet points covering the most relevant considerations from: security/access, data sources, integration with firm systems, ownership/maintenance
- Keep it realistic - show the thinking

**Slide 6 - The Ask**
- Heading: "Next Steps"
- One bold statement: what would the next step be if this went further?
- Who would need to be involved
- What would the pilot look like
- End with a closing line that lands the value proposition

## Instructions
- Infer all content from the project that has been built and the conversation context
- Where information is unclear, make reasonable assumptions that fit a UK law firm context
- Write the full HTML file to `presentation.html` - do not summarise or describe it, write the complete file
- After writing the file, tell the user to open `presentation.html` in their browser to view the presentation
