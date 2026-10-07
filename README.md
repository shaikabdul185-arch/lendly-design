# Lendly — Design

Lendly is a neighborhood lending app: borrow a drill, ladder or tent from someone a few doors down instead of buying one. This repo holds the full UI design: three explored directions, the design system, six app screens and the landing page hero.

**Live preview:** https://shaikabdul185-arch.github.io/lendly-design/

## What's inside

The main file, `Lendly.dc.html`, is one long canvas, in this order:

1. **Step 1 — Explore:** three directions for the Home screen
   - **1a Front Porch:** warm and neighborly. Cream, terracotta and pine, Young Serif + Figtree
   - **1b Toolshed:** clean and practical. Cool grey and cobalt, IBM Plex Sans + Mono, two-column grid
   - **1c Swap Club:** playful and bold. Butter yellow, bright cards, thick outlines, floating dark nav
2. **Step 2 — Design system:** the combined direction, with color tokens (light and dark), type scale, spacing, radii and components
3. **Screens:** six screens in flow order
4. **Landing page:** the hero with the Home screen inside a phone frame

## Design decisions

The final system combines the best part of each direction:

- **From Front Porch:** the warm palette and serif headlines. Lending to a neighbor depends on trust, and this palette feels like it.
- **From Toolshed:** the two-column item grid and monospace distance/owner text, so a long feed stays easy to scan.
- **From Swap Club:** the floating pill nav bar, which keeps a friendly, bold tone without the loud colors.

Corners are rounded throughout. A single terracotta color is used for actions.

## The user flow

Priya finds Marcus's cordless drill on **Home** and opens **Item detail**. She requests Oct 6–8 on the **Request** calendar. The drill then shows on **My Lending** as "Due tomorrow" with a "Start return check-in" button, which leads to **Return check-in**. The sixth screen is the **empty state**.

## Components

Each component is its own reusable file, and every screen uses the same files:

| File | What it is |
|---|---|
| `Button.dc.html` | Primary, secondary and disabled buttons (52px tall, 44px compact) |
| `Chip.dc.html` | Category filter chips |
| `Badge.dc.html` | Status badges: Available, Borrowed, Overdue |
| `Input.dc.html` | Search, text field and message box |
| `ItemCard.dc.html` | Item tile and list cards with distance, owner and status |
| `CheckRow.dc.html` | Checklist row used in Return check-in |
| `BottomNav.dc.html` | Floating pill navigation bar |
| `HomeScreen.dc.html` | Full Home screen, used in the screens row and the landing page |
| `support.js` | Runtime that loads the component files into each page |
| `index.html` | Redirects the site root to `Lendly.dc.html` |

## Accessibility

- Body text contrast ranges from 5.3:1 (terracotta text) to 14:1 (dark ink). White on the terracotta button is 6.0:1.
- Touch targets are 44–52px tall.
- Only disabled button text and crossed-out calendar dates fall below 4.5:1, which WCAG allows for disabled items.

## Run it locally

The pages load component files from the same folder, so open them through a local server rather than by double-clicking:

```bash
git clone https://github.com/shaikabdul185-arch/lendly-design.git
cd lendly-design
python -m http.server 8000
```

Then open http://localhost:8000.

## Not built yet

- Dark-mode screens (dark colors are already defined in the palette)
- A **Map** screen with pins for nearby items (the nav already has a Map tab)
- A clickable prototype: tap calendar days to pick dates, tick the checklist to enable "Complete return"
- Slots for real item photos (items currently use icons on colored tiles)

## Credits

Designed with [Claude Design](https://claude.ai/design) by Abdul Rahman.
