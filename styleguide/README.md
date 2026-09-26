# Banterbull Design System

The complete visual language of **banterbull.com** as it is built today — every
colour, font, type size, spacing step, radius, shadow and component. It is
transcribed directly from the live source in `banterbull-Frontend/landing`
(the home page's inline `<style>` and the shared `new.css`), so the values here
match production exactly, not an approximation.

Banterbull is a worldwide, real-money prediction market. The look is **light,
clean and precise** — near-white surfaces, near-black text, a single hot-orange
accent, and a monospace voice for labels and data. It borrows the calm,
high-contrast surface treatment of a modern product site and pairs it with the
YES/NO teal-and-red of a trading interface.

> **One theme.** The site is intentionally **light-only** — there is no dark
> mode in the source. All tokens below are the light values.

---

## Brand foundation

- **Name:** Banterbull (one word, capital B).
- **Tagline / thesis:** *Trade what you know.* Supporting line: *The world runs
  on opinions. Banterbull runs on knowledge.*
- **Voice:** plain, direct, confident. Short declarative sentences. Says what a
  control does and confirms it plainly. Regulator-first, engineering-first — the
  copy never over-promises. Contacts: `hello@banterbull.com` (general),
  `careers@banterbull.com`, `dpo@banterbull.com` (data protection).

## Logo & brand assets

The marks live in `landing/brand/` and the icons at the site root. (These are
referenced here; the source SVG/PNG files are in the repo and can be embedded as
downloadable assets in this system on request.)

| Asset | File | Use |
| --- | --- | --- |
| Wordmark (orange **b** + black letters) | `brand/banterbull_blackletters_orangeB_transparent.svg` | Top bar and footer on light backgrounds. Rendered at 22px tall in the header, 24px in the footer. |
| Wordmark (orange **b** + white letters) | `brand/banterbull_original_transparent.svg` | For dark backgrounds. |
| Mark only (orange **b**) | `brand/banterbull_mark_transparent.svg` | Square mark; source for `favicon.svg`. |
| Mark on black | `brand/banterbull_mark_black.svg` | Mark on a solid black tile. |
| Favicon (SVG) | `favicon.svg` | Primary tab icon. |
| Favicon 32 | `favicon-32.png` (32×32) | Legacy tab icon. |
| Apple touch icon | `apple-touch-icon.png` (180×180) | iOS home screen. |
| App icon | `icon-512.png` (512×512) | PWA / schema.org logo. |
| Social card | `og-image.png` (1200×630) | Open Graph / Twitter share image. |

## Colour

The whole system runs on one accent (**orange `#FD5101`**) over a near-white /
near-black neutral ramp, plus two trading signals (**teal `#0F766E`** = YES,
**red `#B91C1C`** = NO).

| Token | Value | Role |
| --- | --- | --- |
| `accent` | `#FD5101` | Brand orange — primary buttons, links, focus, live dot, chart lines |
| `accent-hover` | `#FF6A21` | Hover for accent surfaces |
| `yes` | `#0F766E` | YES / positive / success |
| `no` | `#B91C1C` | NO / negative / error |
| `no-bright` | `#FE3D33` | Downward price change on charts only |
| `bg` | `#FFFFFF` | Page background |
| `bg-1` | `#FAFAFA` | Raised surface (cards, steps, footer) |
| `bg-2` | `#F4F4F5` | Hover surface on raised elements |
| `fg` | `#0A0A0A` | Primary text and headings |
| `fg-2` | `rgba(0,0,0,.62)` | Secondary text / body |
| `fg-3` | `rgba(0,0,0,.42)` | Muted text, captions, placeholders |
| `line` | `rgba(0,0,0,.08)` | Hairline borders and dividers |
| `line-2` | `rgba(0,0,0,.16)` | Stronger borders (inputs, ghost button) |

**Market-card component palette** (the Polymarket-style card only):
`market-slate #23272D`, `market-slate-2 #6B727B`, `market-slate-3 #9AA0A8`,
`market-hairline #DFE1E5`, `market-grid #BFC3CA`. The market thumbnail uses a
gradient `linear-gradient(135deg, #FFE3D3, #FD5101)`.

**Rules.** Orange is the only accent — one accent, used sparingly on the thing
that matters most. Teal and red are *signals*, never decoration: reserve them
for YES/NO and success/error. Body text is `fg-2`, not pure black; captions are
`fg-3`. Borders are the `line` tokens, never a grey fill.

## Typography

Two families, both from Google Fonts:

- **Inter Tight** — display and body. Weights **300 / 400 / 500**.
- **Geist Mono** — labels, eyebrows, data. Weights **400 / 500**.

```
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@300;400;500&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Stacks: `--sans: "Inter Tight", ui-sans-serif, system-ui, -apple-system, sans-serif` ·
`--mono: "Geist Mono", ui-monospace, SFMono-Regular, Menlo, monospace`.

**Type scale** (identical on every page):

| Style | Size | Line | Weight | Tracking |
| --- | --- | --- | --- | --- |
| Hero | `clamp(44px, 5.6vw, 84px)` | 0.98 | 300 | −0.05em |
| H1 | `clamp(40px, 5vw, 72px)` | 1.02 | 300 | −0.045em |
| H2 | `clamp(30px, 3.4vw, 44px)` | 1.08 | 300 | −0.035em |
| H3 | 20px | 1.3 | 400 | −0.02em |
| H4 | 16px | 1.4 | 500 | −0.01em |
| Lead | 19px | 1.5 | 400 | −0.01em |
| Body | 16px | 1.5 | 400 | — |
| Small | 14px | 1.5 | 400 | — |
| Fine | 12px | 1.5 | 400 | — |
| Eyebrow (mono) | 12px | 1 | 500 | 0.08em, uppercase |
| Label-sm (mono) | 11px | 1 | 500 | 0.06em, uppercase |
| Meta (mono) | 12px | 1.4 | 400 | 0.04em |

**Rules.** Headings are **light (weight 300)** with **tight negative
letter-spacing** — that combination is the brand's signature. Headings get
`text-wrap: balance`; body and list text get `text-wrap: pretty`. Eyebrows and
labels are monospace, uppercase, letter-spaced. Base body is 16px / 1.5 in
`fg-2`.

## Spacing & layout

- **Max content width:** `1200px` (`.wrap`), centred.
- **Page gutter:** `24px` desktop, `16px` at ≤560px.
- **Spacing scale** (px, as used in the source): 4 · 8 · 12 · 16 · 20 · 24 · 28 ·
  32 · 40 · 48 · 56 · 64 · 72 · 80 · 96. Section vertical padding is 64px
  (56px on mobile); the closing CTA is 96px (72px on mobile).

## Radius

| Token | Value | Use |
| --- | --- | --- |
| `radius-pill` | 999px | Buttons, waitlist field, nav CTA, consent pill |
| `radius-lg` | 20px | Steps grid, why cards, section panels |
| `radius-md` | 16px | Market/board cards, stacked mobile waitlist |
| `radius-sm` | 10px | Market card thumbnail |
| `radius-xs` | 9px | Compact card buttons |
| `radius-chip` | 7px | Chips, amount toggles, source tags |

## Shadows / elevation

Surfaces are mostly flat, separated by `line` borders and the `bg-1` fill.
Shadow is reserved for genuinely floating objects.

| Token | Value | Use |
| --- | --- | --- |
| `shadow-card` | `0 1px 2px rgba(0,0,0,.04), 0 12px 40px rgba(0,0,0,.06)` | Market card |
| `shadow-card-sm` | `0 1px 2px rgba(0,0,0,.04), 0 8px 24px rgba(0,0,0,.05)` | Board card |
| `shadow-pop` | `0 8px 30px rgba(0,0,0,.08)` | Consent pill |
| `shadow-flag` | `0 1px 4px rgba(0,0,0,.12)` | Chart hover flag |

Glass surfaces (sticky header, waitlist field, consent) use
`background: rgba(255,255,255,.72–.92)` with `backdrop-filter: blur(8–16px)`.

## Breakpoints

| Width | What changes |
| --- | --- |
| ≤ 1060px | Hero collapses to one column; market card caps width |
| ≤ 900px | Header nav hidden; steps → 2-up; why-grid & stats → 1 column; footer → 2 columns |
| ≤ 560px | Gutter → 16px; steps → 1 column; waitlist stacks vertically (radius-md); consent goes full-width |

## Components

**Buttons** (`.btn`) — pill, height **44px**, padding `0 22px`, weight 500 /
14px, `transition .2s`.
- `.btn-primary` — `accent` fill, white text; hover `accent-hover`.
- `.btn-ghost` — transparent, `fg` text, `line-2` border; hover 4% black wash.
- `.btn-sm` — height 36px, padding `0 16px`, 13px.

**Waitlist form** (`.waitlist`) — a pill row: `line-2` border, 6px padding,
`radius-pill`, translucent white + blur. Borderless email input; `.btn-primary`
submit. `.form-msg` is the status line (`.ok` → `yes`, `.err` → `no`);
`.form-fine` is the 12px consent line. Stacks vertically at ≤560px.

**Masthead** (`.masthead`) — sticky, 64px, translucent white + `blur(16px)`,
bottom `line` border. Logo 22px; nav links 14px `fg-2` → `fg` on hover; a
`.btn-primary` CTA on the right. Nav hides ≤900px.

**Hero** (`.hero`) — two columns (text + a 540px market card), 48px gap. Mono
eyebrow with a glowing `accent` dot; hero headline; 18px `fg-2` sub; CTA row or
inline waitlist.

**Section head** (`.sec-head`) — mono eyebrow, H2, 17px `fg-2` intro (≤600px).

**Steps** (`.steps` / `.step`) — 4-up hairline grid, `radius-lg`, `bg-1` tiles
with `line` dividers; mono `accent` number, H3 title, 14px body. 2-up ≤900px,
1-up ≤560px.

**Why cards** (`.card`) — `bg-1`, `line` border, `radius-lg`, 24px `accent`
icon; hover raises the border and reveals a soft radial `accent` glow.

**Stat strip** (`.stats` / `.stat`) — 3-up, top `line` border; 56px light figure
with an `accent` emphasis span.

**Closing CTA** (`.close-cta`) — centred, 96px padding, a large blurred radial
`accent` glow behind the H2 and a centred waitlist.

**Market card** (`.mcard`) — the hero's Polymarket-style binary market: slate
text, inline-SVG price chart with `accent` line, dashed `market-grid`,
animated end `ping`, YES (`yes`) / NO (outlined) buttons, range tabs. Uses the
`market-*` palette and `shadow-card`.

**Board** (`.mqcol` / `.bc`) — a vertically auto-scrolling column of compact
market cards (`mqup` 30s marquee, pauses on hover), each with a mini chart and
YES/NO chips (`yes`/`no` tints).

**Consent pill** (`.consent`) — fixed bottom-right pill, `shadow-pop`, glass
background. Note: in production the region-aware consent widget
(`consent/banterbull-consent.js`) is injected by the Cloudflare Worker into
every page; this pill is the lightweight inline fallback.

**Footer** (`footer` / `.fgrid`) — 4-column grid (brand + 3 link columns) over a
mono legal row with the year and legal links.

## Motion & accessibility

- Transitions are quick: `.2s` on interactive elements, `.3s`–`.4s` on card
  hover glows.
- Named animations: `ping` (chart end pulse), `mqup` (board marquee, 30s linear),
  `flu`/`fld` (price-change flash).
- **`prefers-reduced-motion: reduce`** disables the marquee, the chart ping and
  hover motion.
- `scroll-behavior: smooth` with `scroll-padding-top: 64px` for the sticky
  header. `overflow-x: hidden` on the body. Use `tabular-nums` for aligned
  figures.
