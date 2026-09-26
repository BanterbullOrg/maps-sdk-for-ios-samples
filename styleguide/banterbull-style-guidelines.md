---
name: banterbull-design
description: >-
  Apply the Banterbull visual design system when building or editing any
  Banterbull-branded web page, landing page, marketing site, email or UI.
  Use whenever styling banterbull.com or the landing/ site, adding a page or
  component that must match the brand, or answering questions about Banterbull
  brand colours, fonts, type scale, spacing, radius, shadows or design tokens.
  Light-only; one orange accent (#FD5101) with teal/red YES-NO signals, on
  Inter Tight + Geist Mono.
---

# Banterbull design system

Banterbull is a real-money prediction market. The look is **light, clean and
precise**: near-white surfaces, near-black text, a single hot-orange accent, a
monospace voice for labels/data, and teal/red YES-NO trading signals.

**Source of truth:** `landing/index.html` (home page inline `<style>`) and
`landing/new.css` (content pages). Full references in this repo:
`docs/design/design-system.md` (brand book) and `docs/design/design-system.html`
(visual styleguide). Match these exactly — never invent values.

> The site is **light-only by design** — do not add a dark mode unless asked.

## Tokens — paste this `:root`

```css
:root{
  --accent:#FD5101; --accent-hover:#FF6A21;
  --yes:#0F766E; --no:#B91C1C;            /* YES / NO, success / error */
  --bg:#FFF; --bg-1:#FAFAFA; --bg-2:#F4F4F5;
  --line:rgba(0,0,0,.08); --line-2:rgba(0,0,0,.16);
  --fg:#0A0A0A; --fg-2:rgba(0,0,0,.62); --fg-3:rgba(0,0,0,.42);
  --sans:'Inter Tight',ui-sans-serif,system-ui,-apple-system,sans-serif;
  --mono:'Geist Mono',ui-monospace,SFMono-Regular,Menlo,monospace;
  --maxw:1200px;
}
```

Fonts (Google):

```html
<link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@300;400;500&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Market-card-only palette: `#23272D` text · `#6B727B` secondary · `#9AA0A8`
captions · `#DFE1E5` borders · `#BFC3CA` gridlines.

## Type scale

| Style | Size | Line / weight / tracking |
| --- | --- | --- |
| Hero | `clamp(44px,5.6vw,84px)` | 0.98 · 300 · −.05em |
| H1 | `clamp(40px,5vw,72px)` | 1.02 · 300 · −.045em |
| H2 | `clamp(30px,3.4vw,44px)` | 1.08 · 300 · −.035em |
| H3 | 20px | 1.3 · 400 · −.02em |
| H4 | 16px | 1.4 · 500 · −.01em |
| Lead | 19px | 1.5 · 400 · −.01em · `--fg-2` |
| Body | 16px | 1.5 · 400 · `--fg-2` |
| Small / Fine | 14 / 12px | 400 · `--fg-2` / `--fg-3` |
| Eyebrow (mono) | 12px | 500 · .08em · UPPERCASE · `--fg-3` |

## Spacing / radius / shadow

- Spacing scale (px): 4·8·12·16·20·24·28·32·40·48·56·64·72·80·96. Content
  max-width `1200px`; gutter `24px` (→ `16px` ≤560px). Section padding 64px
  (56 mobile); closing CTA 96px.
- Radius: pill `999px` · lg `20px` · md `16px` · sm `10px` · xs `9px` · chip `7px`.
- Shadow (floating objects only): card `0 1px 2px rgba(0,0,0,.04),0 12px 40px rgba(0,0,0,.06)`;
  pop `0 8px 30px rgba(0,0,0,.08)`. Glass = `rgba(255,255,255,.72–.92)` + `blur(8–16px)`.
- Breakpoints: 1060 (hero → 1 col) · 900 (nav hidden, grids collapse) · 560 (mobile gutter, stacks).

## Rules (do / don't)

- **One accent.** Orange only, on the single most important element. Teal/red are
  **signals** (YES/NO, success/error), never decoration.
- Body text is `--fg-2`, captions `--fg-3`; **never pure black body**.
- Separate surfaces with `--line` borders and `--bg-1` fills, **not grey blocks**;
  reserve shadow for genuinely floating objects.
- Headings: **weight 300 + tight negative letter-spacing**, `text-wrap: balance`.
  Body/list: `text-wrap: pretty`. Eyebrows/labels: mono, uppercase, letter-spaced.
- Buttons are pills: `.btn` 44px / `0 22px` / 500·14px; `.btn-primary`
  (accent→accent-hover), `.btn-ghost` (`--line-2` border), `.btn-sm` 36px/13px.
- Respect `prefers-reduced-motion` (disable marquee, chart ping, hover motion).
- Don't introduce new fonts, a second accent, gradients the tokens don't define,
  or emoji as UI markers.

## Waitlist & consent (behaviour, not just style)

- Waitlist forms POST `{ email, seconds_on_page }` to `/api/waitlist`
  (`landing/waitlist-worker.js`, D1-backed). Success → `.form-msg.ok`; error →
  `.form-msg.err`. Don't ship a preview-only handler on real pages.
- Consent is injected site-wide by the Worker (`consent/banterbull-consent.js`);
  don't add a second per-page consent banner.

When in doubt, open `docs/design/design-system.html` or `.md` and copy the exact
value rather than approximating.
