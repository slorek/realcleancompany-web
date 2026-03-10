# Real Clean Company Website — Project Instructions

## Project
Single-page marketing website for The Real Clean Company (domestic & commercial cleaning, Southampton and Isle of Wight).

## Files
- `index.html` — main single-page site
- `styles.css` — all brand styles, layout, animations
- `logo-wide.svg` — landscape logo (desktop, copied from Dropbox "no background wide.svg")
- `logo-square.svg` — square/bare logo (mobile, copied from Dropbox "no background bare.svg")
- `logo.svg` — original copy, no longer referenced in HTML

## Design Tokens
| Token | Value |
|---|---|
| Background gradient | `#bbd4ec` (top) → `#e1ebf5` (bottom), `background-attachment: fixed` |
| Primary navy | `#003b87` |
| Secondary mid-blue | `#2f6dbd` |
| Light blue accent | `#e0ebf4` |
| White | `#ffffff` |

## Typography
- Font: **Crique Grotesk** (brand font) loaded via `@font-face` from `db.onlinewebfonts.com`
  - Medium (weight 100–600): `7ac5b5e00dfb4c46d71852429dc4eafc`
  - Bold (weight 700–800): `0422470d8460bcc298578d02059ad5ca`
  - Heavy (weight 900): `56196b8b12da75c4f5cb429950344edb`
- Headings: `font-weight: 900`, body/labels: `font-weight: 700`

## Key Design Decisions
- **Nav bar**: hidden (`opacity:0; transform:translateY(-100%)`) until user scrolls past the hero logo; revealed via `.nav-visible` class
- **Logo**: `<picture>` element — `logo-wide.svg` on ≥640px, `logo-square.svg` on mobile
- **Decorative elements**: sparkle stars + soap bubbles in a `position:fixed` `.deco-layer` behind all content (`z-index:0`, `pointer-events:none`)
- **Parallax**: JS sets `--py` CSS variable on each deco SVG; CSS applies it via `translate: 0 var(--py, 0px)` (NOT `transform`, to avoid conflicting with float keyframe animations)
- **Float animations**: `floatA/B/C/D` keyframes use `transform:translateY()` — composites independently with `translate`
- **Pop animations**: `popBubble` / `popStar` keyframes animate only `opacity`; applied via inline `style` on selected elements (not CSS classes) to avoid `animation-delay` cascade conflicts
- **Text stroke**: `-webkit-text-stroke` with `paint-order: stroke fill` on blue text over gradient; `#contact .section-title` uses `-webkit-text-stroke-width: 0` to suppress it (white-on-navy needs no stroke)
- **Service cards**: horizontal (`flex-direction: row`) on mobile, vertical column at ≥640px

## Source Assets (Dropbox)
- `/Users/steve/Library/CloudStorage/Dropbox/Documents/Work/Real Clean Company/Logos/`
- `/Users/steve/Library/CloudStorage/Dropbox/Documents/Work/Real Clean Company/Leaflets/`

## Contact Details
- Name: Katie
- Phone: 07972 244852
- Email: info@therealcleancompany.co.uk

## Content
**Services:** Regular Cleaning, Deep Cleaning, Oven Cleaning, End of Tenancy, Carpet Cleaning, Window Cleaning, Commercial Cleaning

**Trust signals:** Fixed price (no clock watching), 11+ years established, all products & equipment provided, COSHH trained, DBS checked & fully insured, checklist every clean, animal friendly, references available

**Service area:** Southampton, Isle of Wight, and surrounding areas
