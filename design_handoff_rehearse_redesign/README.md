# Handoff: Rehearse — Landing Page Palette & Type Redesign

## Overview
A reskin of the Rehearse marketing site (rehearseapps.com) applying a new brand
palette and type system. It re-styles every section of the existing landing page —
nav, hero (with a live-session product card), stats band, "How It Works", the
"Be more human" pillar section, the waitlist form, and the footer — and refines
layout where it helped. The structure and copy stay faithful to the current site.

## About the Design Files
The files in this bundle are **design references created in HTML** — a prototype
showing the intended look, layout, and behavior. They are **not** production code to
copy directly. The task is to **recreate these designs in the Rehearse site's existing
codebase** (whatever framework/components it already uses), following its established
patterns, component library, and conventions.

The main prototype (`Rehearse Redesign Proposal.dc.html`) is authored as a "Design
Component" and includes a proposal wrapper (header, brand reference strip, numbered
annotations, and a "Key decisions" grid). Those wrapper elements are **presentation
scaffolding for the proposal only — do not ship them.** Only the content inside the
browser-chrome mock (the actual page sections) should be implemented.

## Fidelity
**High-fidelity (hifi).** Final colors, typography, spacing, and layout. Recreate the
UI to match, using the codebase's existing components where equivalents exist.

---

## Design Tokens

### Colors
| Token | Hex | Use |
|-------|-----|-----|
| Ember | `#E5471A` | Primary CTA, big stat figures, live dot, checked state, section accents |
| Ink | `#181613` | Body text, dark surfaces (hero product card, pillar section, footer) |
| Blush | `#F6D6C6` | Warm highlight bands (stats), eyebrow pills, waitlist panel |
| Paper | `#FAF9F5` | Page background, cards on dark |
| Stone | `#63625C` | Secondary text, muted labels, borders |

Supporting neutrals used in the mock (derive equivalents from the tokens above):
- Page "desk" behind mock: `#E7E5DE` (proposal only — not part of the page)
- Hairline borders on Paper: `#EDEBE4` / `#D9D6CD`
- Dark card surface: `#12100e`–`#26231f`; muted text on dark: `#b8b6ae`, `#8a8880`
- CTA hover: `#c23c14`

### Typography
Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,600;12..96,700;12..96,800&family=Hanken+Grotesk:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
```
| Role | Family | Weights | Notes |
|------|--------|---------|-------|
| Display / headlines | Bricolage Grotesque | 700–800 | Tight leading (~1.0), letter-spacing −0.02 to −0.025em |
| Body / UI | Hanken Grotesk | 400–600 | line-height ~1.55–1.6 |
| Labels / eyebrows / meta | JetBrains Mono | 400–500 | uppercase, letter-spacing 1.5–2px |

Key sizes (desktop): H1 56px/800; section H3 40px/800; pillar word 30px/800 + qualifier
22px/400 Stone; step title 21px/700; body 14.5–17px; eyebrow/meta 10–12px mono.
Mobile H1 29px; section H3 24px. Minimums respected.

### Radius / shadow
- Cards: 14px; panels/product card: 18px; buttons/pills: 8–9px; browser mock: 16px.
- Product card shadow: `0 24px 50px -24px rgba(24,22,19,0.6)`.

---

## Screens / Views

### 1. Nav (Paper, border-bottom `#EDEBE4`)
Logo lockup left (`rehearse-lockup.png`, ~28px tall). Links: Platform, Why Rehearse,
Early Access (Hanken 15px/500 Ink). Ember pill CTA "Join the waitlist" (11px 20px,
radius 8, Paper text). Flex, space-between, padding 22px 48px.

### 2. Hero (Paper) — 2-col grid `1.05fr 0.95fr`, gap 56, padding 72px 48px
**Left:** Blush eyebrow pill "Leadership Development Platform" (mono, uppercase);
H1 "Rehearse the conversations that drive results before they impact your team";
Stone body paragraph (max 520px); CTA row — Ember button "Join the waitlist" +
text-link "See how it works" (Ink, 2px underline); mono meta "30 min · trained actor ·
AI-personalized feedback".
**Right — live-session product card (Ink `#12100e`, radius 18, padding 16):**
- Header row: Ember dot + "Live session · Underperformance" (Hanken 14/600 Paper), "12:34" (mono Stone) right.
- Body grid `1.55fr 1fr`, gap 14:
  - **Video (left):** Actor photo, `object-fit:cover`, radius 12. Bottom-left "Actor" pill (translucent). Bottom-center control bar: 3 neutral dots + 1 Ember dot in a translucent pill. Bottom-right **picture-in-picture** (38% width, 4:3, radius 9, 2px `#12100e` border) with Manager photo + "YOU" mono label.
  - **Sidebar (right):** "SCENARIO" mono label + "Underperformance: Jordan has missed two deadlines this sprint." Then "LIVE FEEDBACK" label + 3 radio rows: first is **checked** (18px Ember circle, white check icon) "Named the issue directly" (Paper text); other two are outline circles (2px `#4a453e`) "Held the silence" / "Avoided softening the message" (muted `#b8b6ae`).

### 3. Stats band (Blush `#F6D6C6`) — 3-col grid, padding 46px 48px
Three items, each: Bricolage 52px/800 Ember figure + Hanken 15px Ink caption (max 220px).
`82%` promoted with zero leadership training · `4.34 hrs` lost per week to unresolved
conflict · `42%` of team exits are preventable.

### 4. How It Works (Paper) — padding 76px 48px
Ember mono eyebrow "How It Works"; H3 "Practice before it's real". 3-col grid gap 28
of Paper cards (border `#EDEBE4`, radius 14, padding 28): mono step number (01/02/03,
Ember 15/700), Bricolage 21/700 title, Stone 14.5px body.
Steps: Define the scenario · Practice with a trained actor · Receive behavioral feedback.

### 5. Why Rehearse (Ink `#181613`) — padding 76px 48px
Blush mono eyebrow "Why Rehearse"; H3 "Be more human" (Paper). 3-col grid gap 44,
each column: 2px Ember top-border, mono index, Bricolage 30/800 word (Paper) + 22/400
qualifier (Stone), muted body `#b8b6ae`.
Pillars: **Practice** / not theory · **Presence** / not performance · **Personalized** / not generic.

### 6. Waitlist (Paper) — inner Blush panel, radius 18, padding 44
2-col grid `0.9fr 1.1fr`. Left: Ember eyebrow "Early Access", H3 "Pilot programs",
Stone subtitle "Success metrics co-designed and agreed before day one." Right: Paper
card with form fields (Full name, Work email, Company, Company size, Topics — optional)
and Ember submit "Join the waitlist →".

### 7. Footer (Ink) — flex space-between, padding 40px 48px
Left: `rehearse-icon-64.png` (34px, radius 8) + "Rehearse" (Bricolage 20/800 Paper) +
mono "Be more human". Center links: Platform, Early Access. Right: mono "© 2026 Rehearse".

### Mobile
Two representative screens shown in phone frames: (a) hero + condensed live-session card
(actor video with YOU PiP + one checked feedback row); (b) stats + How It Works stacked.
Same tokens; reduced sizes noted above.

---

## Interactions & Behavior
- Nav CTA + hero CTA + waitlist submit → scroll/anchor to the waitlist section (`#waitlist`).
- "See how it works" → anchor to `#platform`.
- Link default/hover colors: `#E5471A` / `#c23c14`. `::selection` background Blush / Ink text.
- Live-session card is a **static product illustration** (no live logic needed on the marketing page). The radio list simply shows one selected state.
- Responsive: single-column stacks below ~900px; keep hero card above or below copy as the grid collapses.

## State Management
None required for the marketing page — it's presentational. (The real waitlist form
already posts on the current site; keep its existing submit handler/validation.)

## Assets
Bundled in this folder — hand to your image pipeline / assets dir:
- `rehearse-lockup.png` — horizontal logo lockup (nav).
- `rehearse-icon-64.png`, `rehearse-icon-180.png`, `rehearse-icon-512.png` — app icon at sizes (footer / favicons / touch icons).
- `manager-you.png` — Manager headshot ("YOU" tile). Placeholder-quality; swap for final.
- `actor.png` — Actor headshot (main video). Placeholder-quality; swap for final.

The two headshots are stand-ins for casting (US + high-end LatAm + Singapore audience,
one Caucasian). Replace with licensed/shot photography before launch.

## Files
- `Rehearse Redesign Proposal.dc.html` — the full annotated prototype (proposal wrapper + desktop + mobile mock). Ship only the page sections inside the browser-chrome mock; ignore the proposal header, numbered annotation badges, and "Key decisions" grid.
