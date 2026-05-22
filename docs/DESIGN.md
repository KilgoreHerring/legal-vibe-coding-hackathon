# Nairo Partners - Design System

All apps and presentations built in this hackathon should use this design system. It reflects the Innovation Team's established visual identity.

When asking Claude to build anything, say: **"Use the Nairo Partners design system from docs/DESIGN.md"** and Claude will apply these styles.

---

## Colour Palette

### Primary Colours
| Token | Hex | Use it for |
|---|---|---|
| `np-dark-blue` | `#435B76` | Body text, secondary buttons, borders |
| `np-teal` | `#068FB1` | Primary actions, links, focus states, key UI elements |
| `np-gold` | `#F9AD23` | Highlights, accents, callouts, badges |

### Neutrals
| Token | Hex | Use it for |
|---|---|---|
| `np-deep-navy` | `#1A2E44` | Headers, navbars, slide backgrounds, dark surfaces |
| `np-mid-grey` | `#666B73` | Secondary text, placeholders, captions |
| `np-pale-grey` | `#E6E8ED` | Borders, dividers, table stripes |
| `np-light-grey` | `#E4E4E4` | Disabled states, subtle backgrounds |
| `np-surface` | `#F5F6F8` | Page background, content areas |
| `np-white` | `#FFFFFF` | Cards, modals, input backgrounds |

### Status / Semantic
| Token | Hex | Use it for |
|---|---|---|
| `np-green` | `#26B58D` | Success, complete, confirmed |
| `np-info-blue` | `#32BEF0` | Information, tips, secondary highlights |
| `np-coral` | `#F0785A` | Errors, warnings, destructive actions |
| `np-amber` | `#F9AD23` | Warnings, pending states |

### Watercolour Accent Palette
Used for decorative gradients and visual softening - not for text or interactive elements.
| Token | Hex |
|---|---|
| `np-sky` | `#A8D4E6` |
| `np-lavender` | `#C4A8D6` |
| `np-pink` | `#E8A0BF` |

---

## Typography

**Font stack:** `"Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif`

No external fonts needed. It renders well on all firm devices.

| Use | Size | Weight | Colour |
|---|---|---|---|
| Page title / H1 | 2rem (32px) | 700 | `#1A2E44` |
| Section heading / H2 | 1.5rem (24px) | 600 | `#1A2E44` |
| Sub-heading / H3 | 1.125rem (18px) | 600 | `#435B76` |
| Body text | 1rem (16px) | 400 | `#435B76` |
| Small / caption | 0.875rem (14px) | 400 | `#666B73` |
| Label | 0.875rem (14px) | 500 | `#435B76` |

---

## Layout & Spacing

- **Page background:** `#F5F6F8`
- **Max content width:** `1200px`, centred
- **Card background:** `#FFFFFF` with `border: 1px solid #E6E8ED` and `border-radius: 8px`
- **Card shadow:** `box-shadow: 0 1px 4px rgba(26, 46, 68, 0.08)`
- **Base spacing unit:** `8px` - use multiples (8, 16, 24, 32, 48)
- **Border radius:** `6px` for inputs/buttons, `8px` for cards, `12px` for large panels

---

## Components

### Buttons

**Primary (teal)** - main actions
```css
background: #068FB1; color: #FFFFFF; border: none;
padding: 10px 20px; border-radius: 6px; font-weight: 500;
```
Hover: `background: #057a98`

**Secondary (outlined)** - secondary actions
```css
background: transparent; color: #435B76;
border: 1.5px solid #435B76; padding: 10px 20px; border-radius: 6px;
```
Hover: `background: #F5F6F8`

**Gold accent** - highlights, CTAs
```css
background: #F9AD23; color: #1A2E44; border: none;
padding: 10px 20px; border-radius: 6px; font-weight: 600;
```

### Cards
```css
background: #FFFFFF;
border: 1px solid #E6E8ED;
border-radius: 8px;
padding: 24px;
box-shadow: 0 1px 4px rgba(26, 46, 68, 0.08);
```

### Form Inputs
```css
background: #FFFFFF;
border: 1.5px solid #E6E8ED;
border-radius: 6px;
padding: 10px 14px;
color: #435B76;
font-size: 1rem;
```
Focus: `border-color: #068FB1; outline: none; box-shadow: 0 0 0 3px rgba(6, 143, 177, 0.15)`

### Status Badges
```css
/* Success */   background: #E8FAF5; color: #26B58D; border: 1px solid #26B58D;
/* Warning */   background: #FEF5E4; color: #F9AD23; border: 1px solid #F9AD23;
/* Error */     background: #FEF0EC; color: #F0785A; border: 1px solid #F0785A;
/* Info */      background: #E6F7FD; color: #068FB1; border: 1px solid #32BEF0;
```
All badges: `padding: 3px 10px; border-radius: 999px; font-size: 0.8rem; font-weight: 500`

### Navigation / Header
```css
background: #1A2E44; color: #FFFFFF;
padding: 16px 32px;
```
Nav links: `color: #E6E8ED;` Active: `color: #F9AD23`

---

## Gradient Patterns

**Watercolour accent** - subtle decorative background (opacity 0.12)
```css
background: linear-gradient(135deg, #A8D4E6 0%, #C4A8D6 40%, #E8A0BF 70%, #068FB1 100%);
```

**Watercolour wash** - stronger hero/banner use (opacity 0.25)
```css
background: linear-gradient(135deg, #A8D4E6 0%, #C4A8D6 35%, #E8A0BF 65%, #068FB1 100%);
```

**Teal gradient** - bars, progress, accents
```css
background: linear-gradient(90deg, #068FB1 0%, #32BEF0 100%);
```

---

## CSS Starter Block

Paste this `<style>` block into any self-contained HTML app to apply the Nairo Partners design system. No Tailwind or external dependencies needed.

```html
<style>
  /* Nairo Partners - Design Tokens */
  :root {
    --np-dark-blue:   #435B76;
    --np-teal:        #068FB1;
    --np-teal-hover:  #057a98;
    --np-gold:        #F9AD23;
    --np-deep-navy:   #1A2E44;
    --np-mid-grey:    #666B73;
    --np-pale-grey:   #E6E8ED;
    --np-light-grey:  #E4E4E4;
    --np-surface:     #F5F6F8;
    --np-white:       #FFFFFF;
    --np-green:       #26B58D;
    --np-info-blue:   #32BEF0;
    --np-coral:       #F0785A;
    --np-amber:       #F9AD23;
    --np-sky:         #A8D4E6;
    --np-lavender:    #C4A8D6;
    --np-pink:        #E8A0BF;
    --font: "Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif;
    --radius-sm: 6px;
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-card: 0 1px 4px rgba(26, 46, 68, 0.08);
    --shadow-raised: 0 4px 16px rgba(26, 46, 68, 0.12);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--np-surface);
    color: var(--np-dark-blue);
    font-family: var(--font);
    font-size: 1rem;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  h1 { font-size: 2rem;    font-weight: 700; color: var(--np-deep-navy); }
  h2 { font-size: 1.5rem;  font-weight: 600; color: var(--np-deep-navy); }
  h3 { font-size: 1.125rem; font-weight: 600; color: var(--np-dark-blue); }
  p  { color: var(--np-dark-blue); }
  small, .caption { font-size: 0.875rem; color: var(--np-mid-grey); }

  /* Navigation */
  nav {
    background: var(--np-deep-navy);
    color: var(--np-white);
    padding: 16px 32px;
    display: flex;
    align-items: center;
    gap: 24px;
  }
  nav a { color: var(--np-pale-grey); text-decoration: none; font-size: 0.9rem; }
  nav a:hover, nav a.active { color: var(--np-gold); }
  .nav-brand { font-weight: 700; font-size: 1.1rem; color: var(--np-white); }

  /* Layout */
  .container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
  .page { padding: 32px 24px; max-width: 1200px; margin: 0 auto; }

  /* Cards */
  .card {
    background: var(--np-white);
    border: 1px solid var(--np-pale-grey);
    border-radius: var(--radius-md);
    padding: 24px;
    box-shadow: var(--shadow-card);
  }
  .card-raised { box-shadow: var(--shadow-raised); }

  /* Buttons */
  .btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 20px; border-radius: var(--radius-sm);
    font-family: var(--font); font-size: 0.95rem; font-weight: 500;
    cursor: pointer; border: none; text-decoration: none;
    transition: background 0.15s, box-shadow 0.15s;
  }
  .btn-primary   { background: var(--np-teal); color: var(--np-white); }
  .btn-primary:hover { background: var(--np-teal-hover); }
  .btn-secondary { background: transparent; color: var(--np-dark-blue); border: 1.5px solid var(--np-dark-blue); }
  .btn-secondary:hover { background: var(--np-surface); }
  .btn-gold      { background: var(--np-gold); color: var(--np-deep-navy); font-weight: 600; }
  .btn-gold:hover { background: #e09c1a; }
  .btn:disabled  { opacity: 0.45; cursor: not-allowed; }

  /* Forms */
  .form-group { display: flex; flex-direction: column; gap: 6px; margin-bottom: 20px; }
  label { font-size: 0.875rem; font-weight: 500; color: var(--np-dark-blue); }
  input, select, textarea {
    background: var(--np-white);
    border: 1.5px solid var(--np-pale-grey);
    border-radius: var(--radius-sm);
    padding: 10px 14px;
    color: var(--np-dark-blue);
    font-family: var(--font);
    font-size: 1rem;
    width: 100%;
    transition: border-color 0.15s, box-shadow 0.15s;
  }
  input:focus, select:focus, textarea:focus {
    border-color: var(--np-teal);
    outline: none;
    box-shadow: 0 0 0 3px rgba(6, 143, 177, 0.15);
  }
  textarea { resize: vertical; min-height: 100px; }

  /* Badges */
  .badge {
    display: inline-block;
    padding: 3px 10px; border-radius: 999px;
    font-size: 0.8rem; font-weight: 500;
  }
  .badge-success { background: #E8FAF5; color: var(--np-green);   border: 1px solid var(--np-green); }
  .badge-warning { background: #FEF5E4; color: var(--np-amber);   border: 1px solid var(--np-amber); }
  .badge-error   { background: #FEF0EC; color: var(--np-coral);   border: 1px solid var(--np-coral); }
  .badge-info    { background: #E6F7FD; color: var(--np-teal);    border: 1px solid var(--np-info-blue); }

  /* Dividers */
  hr { border: none; border-top: 1px solid var(--np-pale-grey); margin: 24px 0; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--np-mid-grey); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--np-dark-blue); }

  /* Decorative gradients */
  .watercolour-accent {
    background: linear-gradient(135deg, #A8D4E6 0%, #C4A8D6 40%, #E8A0BF 70%, #068FB1 100%);
    opacity: 0.12;
  }
  .teal-gradient { background: linear-gradient(90deg, #068FB1 0%, #32BEF0 100%); }
</style>
```

---

## Presentation Colours (for `/present` slides)

The `/present` command uses a dark theme. Map the design tokens to slides as follows:

| Slide element | Value |
|---|---|
| Slide background | `#1A2E44` (deep-navy) |
| Heading text | `#FFFFFF` |
| Body text | `#E6E8ED` (pale-grey) |
| Accent / highlight | `#068FB1` (teal) |
| Gold callout | `#F9AD23` |
| Decorative gradient | Watercolour (sky → lavender → pink → teal) |
| Progress bar / divider | Teal gradient |
