# Design Reference — Jaehong Kim Personal Website

## Color Palette

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#F5F3F0` | Page background (Pantone Cloud Dancer 2026) |
| `--text` | `#0a0a0a` | Primary text, headings |
| `--text-body` | `#374151` | Body copy (bio, research, pub titles) |
| `--text-secondary` | `#6b6860` | Warm gray — nav links, dates, labels |
| `--border` | `#e2ddd8` | All dividers and borders (warm undertone) |
| `--accent` | `#4f46e5` | Indigo — venue badges, active nav, link hover |
| `--accent-bg` | `#eef2ff` | Indigo tint — venue badge background, pub-link hover bg |
| Amber | `#b45309` / `#fffbeb` | Under Review badge, award badge, Cum Laude |
| Amber border | `#fde68a` | Award badge border only |

All secondary/muted text uses `--text-secondary` (#6b6860) — warm stone, not cool gray.

---

## Typography

| Element | Size | Weight | Notes |
|---|---|---|---|
| `h1` (name) | 24px | 600 | `letter-spacing: -0.02em` |
| `h2` (section label) | 12.5px | 600 | Uppercase, `letter-spacing: 0.08em` |
| Body base | 15px | 400 | `line-height: 1.6` |
| Profile bio | 15px | 400 | `line-height: 1.75` |
| Research paragraphs | 15px | 400 | `line-height: 1.8` |
| Pub title | 15px | 500 | — |
| Ongoing title | 15px | 400 | — |
| News text | 15px | 400 | — |
| Edu degree | 15px | 500 | — |
| Nav name | 14px | 600 | — |
| Profile links | 14px | 400 | — |
| News date | 14px | 400 | `font-variant-numeric: tabular-nums` |
| Edu school | 14px | 400 | — |
| Edu year | 14px | 400 | — |
| Nav links | 13px | 400 | — |
| Pub links | 13px | 400 | Border button style |
| Edu note | 13px | 400 | Italic |
| Venue badge | 12px | 600 | Uppercase |
| Status badge | 12px | 600 | Uppercase |
| Footer | 12px | 400 | — |
| Award badge | 11px | 500 | — |

**Font stack:** `-apple-system, BlinkMacSystemFont, 'Apple SD Gothic Neo', 'Helvetica Neue', sans-serif`

---

## Layout

- Max width: `720px`, centered
- Body padding: `0 24px 96px`
- Nav height: `52px`, sticky, `backdrop-filter: blur(10px)`, `rgba(245,243,240,0.88)`
- Scroll padding top: `64px`

### Section spacing

| | Top | Bottom |
|---|---|---|
| First section | 64px | 64px |
| `section + section` | 56px | 64px |
| `#profile` | 64px | 0 |

### Profile grid

- Columns: `148px 1fr`, gap `32px`, `align-items: stretch`
- Photo: `148px × 100%`, `min-height: 180px`, `border-radius: 10px`, `box-shadow: 0 2px 12px rgba(0,0,0,0.07)`
- Mobile (≤580px): single column, photo becomes `88px` circle

---

## Interaction

| Element | Hover | Active |
|---|---|---|
| Nav links | `color: --text`, `border-bottom: --border` | `color: --text`, `border-bottom: --accent` |
| Profile links | `color: --text`, `border-bottom: --border` | — |
| Bio links | `text-decoration-color: --accent` | — |
| Pub links | `border: --accent`, `bg: --accent-bg` | — |

All transitions: `0.15s` on `color` and `border-color`.

**Active nav logic:** `window.innerHeight * 0.65` viewport threshold — last section whose top is within 65% of viewport height becomes active. Scroll listener with `passive: true`.

---

## Badges

| Type | Color | Background | Border | Usage |
|---|---|---|---|---|
| Venue | `--accent` | `--accent-bg` | none | Conference name |
| Under Review | `#b45309` | `#fffbeb` | none | Ongoing Work |
| Ongoing | `--text-secondary` | `#f3f4f6` | none | Ongoing Work |
| Award | `#b45309` | `#fffbeb` | `#fde68a` | Best Paper nomination |
| Cum Laude | `#b45309` | none | none | Inline italic in degree line |

---

## Section Order

1. Profile
2. News
3. Research
4. Publications
5. Ongoing Work
6. Education

---

## Responsive (≤580px)

- Nav gap: `24px → 14px`, font: `13px → 12px`
- Profile: single column, photo `88px` circle
- Section padding: `64/56px → 48/44px`
- Edu items: stack vertically

---

## Miscellaneous

- Email: JS-constructed at runtime (anti-crawler). No plain text in HTML.
- Flag emoji in News: 🇩🇪 on Germany arrival, 🇰🇷 on Korea return.
- News date format: `Mon YYYY` (no brackets).
- Nav name "Jaehong Kim" links to `#` (scroll to top).
