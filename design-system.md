# john-site Design System

## Colors

| Token | Value | Use for |
|---|---|---|
| `--color-ink` | `#121212` | Headings, primary text on light, dark section backgrounds |
| `--color-ink-soft` | `rgb(18 18 18 / 0.75)` | Body copy, eyebrows, ticker text |
| `--color-ink-faint` | `rgb(18 18 18 / 0.55)` | Fine print, footer copy |
| `--color-button` | `#080808` | Solid button background |
| `--color-bg` | `#ffffff` | Page background |
| `--color-surface` | `#f3f3f3` | Alternating sections, image backdrops |
| `--color-border` | `rgb(8 8 8 / 0.14)` | All borders, dividers, input underlines |
| `--color-red` | `#8f1d1d` | Numerals, small emphasis marks — never body text |
| `--color-gold` | `#b8905a` | Serif quotes, logo accents on dark |
| `--color-blue` | `#334fb4` | Reserved — do not use without adding a pattern |
| `--color-white` | `#ffffff` | Text on dark, solid button labels |

## Typography

| Token | Value | Use for |
|---|---|---|
| `--font-body` | `"Assistant", system-ui, sans-serif` | All sans text |
| `--font-serif` | `Georgia, "Times New Roman", serif` | Quotes, motto lines |

Self-hosted woff2, weights `400` `600` `700`, `font-display: swap`. Body letter-spacing `0.06em`.

| Token | Value | Use for |
|---|---|---|
| `--text-micro` | `0.625rem` | Ticker items |
| `--text-caption` | `0.6875rem` | Eyebrows, buttons, numerals, statuses |
| `--text-sm` | `0.875rem` | Product titles, nav, footer |
| `--text-base` | `1rem` | Body text (1.0625rem at `48rem`) |
| `--text-lead` | `1.125rem` | Hero subtitle |
| `--text-h3` | `1.25rem` | Card titles, column headings |
| `--text-h2` | `2rem` | Section headings (3.5rem at `64rem`) |
| `--text-h1` | `2.5rem` | Hero heading — no desktop bump |
| `--text-serif` | `2.4rem` | Serif quote lines |

Line height: `1.8` body, `1.1` headings. Heading weight `400` — scale carries emphasis, not boldness.

| Pattern | Size | Weight | Tracking | Transform |
|---|---|---|---|---|
| Eyebrow | `--text-caption` | `600` | `0.22em` | uppercase |
| Button label | `--text-caption` | `700` | `0.16em` | uppercase |
| Ticker item | `--text-micro` | `700` | `0.18em` | uppercase |
| Numeral | `--text-caption` | `700` | `0.24em` | none |
| Status line | `--text-caption` | `600` | `0.14em` | uppercase |

## Spacing

| Token | Value | Use for |
|---|---|---|
| `--space-1` | `0.25rem` | Icon gaps |
| `--space-2` | `0.5rem` | Inside components |
| `--space-3` | `1rem` | Between related elements |
| `--space-4` | `1.5rem` | Grid gaps mobile, card padding |
| `--space-5` | `2.5rem` | Between elements in a section |
| `--space-6` | `4rem` | Between sections (mobile) |
| `--space-7` | `6rem` | Between sections (desktop) |
| `--space-8` | `8rem` | Hero vertical padding (desktop) |

## Radius, Borders, Shadows

| Token | Value | Use for |
|---|---|---|
| `--radius` | `0` | Everything — no rounded corners anywhere |
| `--border-width` | `1px` | All borders |
| `--shadow` | `none` | Shadows are not used in this system |

## Breakpoints

| Token | Min-width | Target |
|---|---|---|
| `--bp-md` | `48rem` | Tablets, inline nav |
| `--bp-lg` | `64rem` | Desktops, split hero |

## Motion

| Token | Value | Use for |
|---|---|---|
| `--transition` | `150ms ease` | Color, opacity, underline states |

Animate only `color`, `background-color`, `border-color`, `opacity`, `transform`. Respect `prefers-reduced-motion`.

## Layout

| Property | Value |
|---|---|
| Page width | `75rem` max, full-bleed sections |
| Container side padding | `1.25rem` mobile, `2.5rem` desktop |
| Section vertical padding | `--space-6` mobile, `--space-7` desktop |
| Grid gaps | `0.25rem` mobile, `0.5rem` desktop |
| Product grid | 2 columns mobile, 3 at `64rem` |
| Value columns | 1 column mobile, 3 at `64rem`, divided by hairlines |

## Components

### Announcement Bar

Full-width, `--color-surface` background, bottom hairline. Text: `--text-caption`, weight `600`, tracking `0.14em`, uppercase, centered, `--color-ink-soft`. Height `2.5rem`.

### Header

White background, bottom hairline. Three zones: menu button (mobile only) left, wordmark center, icons right. At `48rem`: wordmark left, inline nav center-left, icons right. Wordmark: `--text-sm`, weight `700`, tracking `0.35em`, uppercase. Nav links: `--text-caption`, weight `600`, tracking `0.14em`, uppercase, `--color-ink-soft`, hover `--color-ink`. Header height `4rem`. Mobile nav opens as full-width drawer below header: white, hairline bottom, stacked links with `--space-3` padding.

### Button

| Variant | Background | Text | Border |
|---|---|---|---|
| `.btn--solid` | `--color-button` | `--color-white` | none |
| `.btn--underline` | transparent | `--color-ink` | none — 1px underline offset `0.3em` |

Both: `--text-caption`, weight `700`, tracking `0.16em`, uppercase, radius `0`, min height `2.75rem`, padding `0 1.75rem`. Hover: solid → background `#000`; underline → underline thins to `0.06em` and color shifts to `--color-ink-soft`. Focus: 2px `--color-ink` outline, offset `2px`.

### Hero

Split at `64rem`: text left, image right, equal halves, `--space-6` gap. Stacked and centered on mobile. Eyebrow top. Heading `--text-h1`, weight `400`, line height `1.1`. Subtitle `--text-lead`, `--color-ink-soft`, max-width `36rem`. Actions row: solid button + underline link, gap `--space-3`. Image: full-bleed right half, `--color-surface` backdrop, no radius, no shadow. Mobile padding `--space-6` block; desktop `--space-8`.

### Ticker

Full-width strip, hairline top and bottom borders, transparent background. Three cells divided by vertical hairlines, equal width, centered text: `--text-micro`, weight `700`, tracking `0.18em`, uppercase, `--color-ink-soft`. Height `2.75rem`. Stacks to single column with horizontal hairlines on mobile.

### Product Card

No border, no radius, no shadow. Image area: `--color-surface` background, aspect ratio 4:5, garment graphic centered. Below image, left-aligned: title row (`--text-sm`, weight `600`, `--color-ink`) with price right-aligned same size; status line (`--text-caption`, `--color-ink-soft`, uppercase); link `VIEW PRODUCT →` (`--text-caption`, weight `600`, tracking `0.14em`, uppercase, underline on hover). Grid gap `0.5rem`; text block padding-top `--space-3`.

### Manifesto Band

Full-bleed `--color-ink` background, white text, padding `--space-7` block. Eyebrow in `--color-gold`. Heading `--text-h2`, weight `400`, `--color-white`, max-width `36rem`. One supporting line `--text-sm`, `rgb(255 255 255 / 0.7)`. One underline link, white. Left-aligned, container width.

### Value Columns

Top and bottom hairline borders. Three equal columns divided by vertical hairlines. Each: numeral (`--color-red`, tracking `0.24em`), heading (`--text-h3`, weight `600`, margin-top `--space-3`), body (`--text-sm`, `--color-ink-soft`, max-width `18rem`). Padding `--space-5` block. Stacks with horizontal hairlines on mobile.

### Serif Band

Full-bleed `--color-ink` background. Heading `--text-h2`, `--color-white`. Serif line `--text-serif`, `--font-serif`, `--color-white`, line height `1.3`. Caption `--text-caption`, `rgb(255 255 255 / 0.6)`. Quote `--text-lead`, `--font-serif`, `--color-gold`, max-width `40rem`. Left-aligned, container width, padding `--space-7` block.

### Newsletter

Centered, `--color-bg` background, top hairline. Label `--text-sm`. Input: borderless except 1px bottom border `--color-border`, `--text-sm`, padding `--space-2` 0, width `18rem`; focus border `--color-ink`. Submit: arrow `→` button, no border, `--color-ink`. One column, gap `--space-3`.

### Footer

Single row, hairline top border, padding `--space-3` block. Copy `--text-caption`, `--color-ink-faint`. Links inline, same size, `--color-ink-soft`, hover `--color-ink`. Space-between at `48rem`, stacked centered on mobile.

## Accessibility

- Text contrast 4.5:1 minimum (3:1 for text ≥ `1.5rem` bold)
- Visible `:focus-visible` on every interactive element
- `alt` on every `<img>`; `alt=""` for decorative
- One `<h1>` per page; no skipped heading levels
- Full keyboard operation
- Touch targets 44×44px minimum
- Form errors via `aria-describedby` and `aria-invalid`
- Respect `prefers-reduced-motion`

## Rules

- Tokens only — no raw hex values or pixel sizes in component CSS
- Radius zero, shadows none — structure comes from hairlines and whitespace
- Uppercase + tracking is the voice of the system; never letterspace lowercase body text
- One solid button per view; secondary actions are underlined text
- Red and gold are accents only — never backgrounds, never body text
- Real content only — no stock photos or placeholder text
- Mobile styles first, breakpoints after
- Semantic elements: `header`, `nav`, `main`, `section`, `footer`
- `rem` for all font sizes
- New values become tokens before use
