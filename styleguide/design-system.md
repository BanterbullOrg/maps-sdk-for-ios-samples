# Banterbull Design System

The complete visual language of **banterbull.com** as built today. Every value
here is transcribed directly from the live source in `landing/` (the home page's
inline `<style>` and the shared `new.css`), so it matches production exactly.

Banterbull is a worldwide, real-money prediction market. The look is **light,
clean and precise**: near-white surfaces, near-black text, a single hot-orange
accent, and a monospace voice for labels and data — paired with the YES/NO
teal-and-red of a trading interface.

> **One theme.** The site is intentionally **light-only** — there is no dark
> mode in the source.

---

## 1. Brand foundation

- **Name:** Banterbull (one word, capital B).
- **Thesis / tagline:** *Trade what you know.* — *The world runs on opinions.
  Banterbull runs on knowledge.*
- **Voice:** plain, direct, confident. Short declarative sentences. Regulator-first,
  engineering-first; never over-promises.
- **Contacts:** `hello@banterbull.com` · `careers@banterbull.com` ·
  `dpo@banterbull.com`.

## 2. Logo & brand assets

Marks live in `landing/brand/`; icons at the site root.

| Asset | File | Use |
| --- | --- | --- |
| Wordmark (orange **b** + black letters) | `brand/banterbull_blackletters_orangeB_transparent.svg` | Header (22px tall) & footer (24px) on light |
| Wordmark (orange **b** + white letters) | `brand/banterbull_original_transparent.svg` | Dark backgrounds |
| Mark only | `brand/banterbull_mark_transparent.svg` | Square mark; source for `favicon.svg` |
| Mark on black | `brand/banterbull_mark_black.svg` | Mark on solid black |
| Favicon | `favicon.svg` · `favicon-32.png` (32) | Browser tab |
| Apple touch icon | `apple-touch-icon.png` (180) | iOS home screen |
| App icon | `icon-512.png` (512) | PWA / schema.org logo |
| Social card | `og-image.png` (1200×630) | Open Graph / Twitter |

## 3. Colour

One accent (**orange `#FD5101`**) over a near-white → near-black neutral ramp,
plus two trading signals (**teal = YES**, **red = NO**).

| Token | Value | Role |
| --- | --- | --- |
| `--accent` | `#FD5101` | Brand orange — primary buttons, links, focus, live dot, chart lines |
| `--accent-hover` | `#FF6A21` | Hover for accent surfaces |
| `--yes` | `#0F766E` | YES / positive / success |
| `--no` | `#B91C1C` | NO / negative / error |
| *(down)* | `#FE3D33` | Brighter red — downward price change on charts only |
| `--bg` | `#FFFFFF` | Page background |
| `--bg-1` | `#FAFAFA` | Raised surface (cards, steps, footer) |
| `--bg-2` | `#F4F4F5` | Hover surface on raised elements |
| `--fg` | `#0A0A0A` | Primary text & headings |
| `--fg-2` | `rgba(0,0,0,.62)` | Secondary text / body |
| `--fg-3` | `rgba(0,0,0,.42)` | Muted text, captions, placeholders |
| `--line` | `rgba(0,0,0,.08)` | Hairline borders / dividers |
| `--line-2` | `rgba(0,0,0,.16)` | Stronger borders (inputs, ghost button) |

**Market-card palette** (Polymarket-style card only): `#23272D` text, `#6B727B`
secondary, `#9AA0A8` captions, `#DFE1E5` borders, `#BFC3CA` gridlines; thumbnail
gradient `linear-gradient(135deg,#FFE3D3,#FD5101)`.

**Rules.** Orange is the only accent — used sparingly on the one thing that
matters most. Teal and red are *signals* (YES/NO, success/error), never
decoration. Body text is `--fg-2`, captions `--fg-3`; borders use the `--line`
tokens, never a grey fill.

## 4. Typography

- **Inter Tight** — display & body. Weights **300 / 400 / 500**.
- **Geist Mono** — labels, eyebrows, data. Weights **400 / 500**.

```html
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@300;400;500&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
```

```css
--sans: "Inter Tight", ui-sans-serif, system-ui, -apple-system, sans-serif;
--mono: "Geist Mono", ui-monospace, SFMono-Regular, Menlo, monospace;
```

| Style | Size | Line | Weight | Tracking |
| --- | --- | --- | --- | --- |
| Hero | `clamp(44px,5.6vw,84px)` | 0.98 | 300 | −0.05em |
| H1 | `clamp(40px,5vw,72px)` | 1.02 | 300 | −0.045em |
| H2 | `clamp(30px,3.4vw,44px)` | 1.08 | 300 | −0.035em |
| H3 | 20px | 1.3 | 400 | −0.02em |
| H4 | 16px | 1.4 | 500 | −0.01em |
| Lead | 19px | 1.5 | 400 | −0.01em |
| Body | 16px | 1.5 | 400 | — |
| Small | 14px | 1.5 | 400 | — |
| Fine | 12px | 1.5 | 400 | — |
| Eyebrow (mono) | 12px | 1 | 500 | 0.08em, uppercase |
| Label-sm (mono) | 11px | 1 | 500 | 0.06em, uppercase |
| Meta (mono) | 12px | 1.4 | 400 | 0.04em |

**Rules.** Headings are **light (300)** with **tight negative letter-spacing** —
the brand's signature. Headings get `text-wrap: balance`; body/list text gets
`text-wrap: pretty`. Eyebrows/labels are mono, uppercase, letter-spaced.

## 5. Spacing & layout

- **Max content width:** `1200px` (`.wrap`), centred.
- **Page gutter:** `24px` desktop, `16px` at ≤560px.
- **Scale (px):** 4 · 8 · 12 · 16 · 20 · 24 · 28 · 32 · 40 · 48 · 56 · 64 · 72 ·
  80 · 96. Section padding 64px (56 mobile); closing CTA 96px (72 mobile).

## 6. Radius

| Token | Value | Use |
| --- | --- | --- |
| `--radius-pill` | 999px | Buttons, waitlist field, nav CTA, consent |
| `--radius-lg` | 20px | Steps grid, why cards, panels |
| `--radius-md` | 16px | Market/board cards, stacked mobile waitlist |
| `--radius-sm` | 10px | Market thumbnail |
| `--radius-xs` | 9px | Compact card buttons |
| `--radius-chip` | 7px | Chips, toggles, source tags |

## 7. Shadows / elevation

Surfaces are mostly flat, separated by `--line` borders and `--bg-1` fills.
Shadow is reserved for floating objects. Glass surfaces (header, waitlist,
consent) use `rgba(255,255,255,.72–.92)` + `backdrop-filter: blur(8–16px)`.

| Token | Value | Use |
| --- | --- | --- |
| card | `0 1px 2px rgba(0,0,0,.04), 0 12px 40px rgba(0,0,0,.06)` | Market card |
| card-sm | `0 1px 2px rgba(0,0,0,.04), 0 8px 24px rgba(0,0,0,.05)` | Board card |
| pop | `0 8px 30px rgba(0,0,0,.08)` | Consent pill |
| flag | `0 1px 4px rgba(0,0,0,.12)` | Chart hover flag |

## 8. Breakpoints

| Width | What changes |
| --- | --- |
| ≤ 1060px | Hero → one column; market card caps width |
| ≤ 900px | Header nav hidden; steps → 2-up; why-grid & stats → 1 col; footer → 2 col |
| ≤ 560px | Gutter → 16px; steps → 1 col; waitlist stacks; consent full-width |

## 9. Components

- **Buttons** (`.btn`) — pill, 44px, `0 22px`, 500/14px, `transition .2s`.
  `.btn-primary` (accent → accent-hover), `.btn-ghost` (transparent, `--line-2`
  border), `.btn-sm` (36px / 13px).
- **Waitlist** (`.waitlist`) — pill row, `--line-2` border, 6px pad, glass; email
  input + primary submit. `.form-msg` (`.ok`→yes, `.err`→no); `.form-fine` (12px
  consent). Stacks at ≤560px. Posts `{email, seconds_on_page}` to `/api/waitlist`.
- **Masthead** (`.masthead`) — sticky, 64px, glass + `blur(16px)`, `--line`
  bottom. Logo 22px, nav 14px `--fg-2`→`--fg`, primary CTA right. Nav hides ≤900px.
- **Hero** (`.hero`) — two columns (text + 540px market card), 48px gap; mono
  eyebrow with glowing accent dot.
- **Section head** (`.sec-head`) — mono eyebrow, H2, 17px `--fg-2` intro.
- **Steps** (`.steps`/`.step`) — 4-up hairline grid, `--radius-lg`, `--bg-1`
  tiles; mono accent number, H3, 14px body.
- **Why cards** (`.card`) — `--bg-1`, `--line`, `--radius-lg`, 24px accent icon;
  hover raises border + soft radial accent glow.
- **Stat strip** (`.stats`/`.stat`) — 3-up; 56px light figure w/ accent emphasis.
- **Closing CTA** (`.close-cta`) — centred, 96px pad, blurred radial accent glow,
  centred waitlist.
- **Market card** (`.mcard`) — binary market: slate text, inline-SVG accent chart,
  dashed grid, animated end `ping`, YES/NO buttons, range tabs; `shadow-card`.
- **Board** (`.mqcol`/`.bc`) — vertically auto-scrolling column of mini market
  cards (`mqup` 30s marquee, pauses on hover).
- **Consent pill** (`.consent`) — fixed bottom-right glass pill, `shadow-pop`.
  In production the region-aware widget `consent/banterbull-consent.js` is
  injected site-wide by the Cloudflare Worker.
- **Footer** — 4-column grid + mono legal row (year + legal links).

## 10. Motion & accessibility

- Transitions `.2s` interactive, `.3s–.4s` card-hover glows.
- Animations: `ping` (chart pulse), `mqup` (30s marquee), `flu`/`fld` (price
  flash). All disabled under `prefers-reduced-motion: reduce`.
- `scroll-behavior: smooth` + `scroll-padding-top: 64px`; `overflow-x: hidden`
  on body; `tabular-nums` for aligned figures.

---

*Live reference (visual): [`design-system.html`](./design-system.html). Interactive
version: the "Banterbull" Design System artifact.*
