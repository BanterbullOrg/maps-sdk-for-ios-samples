# Banterbull Design System — pointer

> **This is a pointer, not the source of truth.** The canonical, org-wide
> Banterbull design system lives in the **frontend** repo:
> **[`banterbull-Frontend/docs/design/`](https://github.com/BanterbullOrg/banterbull-frontend/blob/main/docs/design/README.md)**.
> Do not edit the brand here — change it there. This file exists only so this
> repo has the brand essentials on hand and knows where the full reference is.

Banterbull is a worldwide, real-money prediction market. The look is **light,
clean and precise**: near-white surfaces, near-black text, a single hot-orange
accent, and a monospace voice for labels and data — paired with the YES/NO
teal-and-red of a trading interface. The site is **light-only by design** (no
dark mode).

## Full reference (canonical)

- **Brand book:** [`docs/design/design-system.md`](https://github.com/BanterbullOrg/banterbull-frontend/blob/main/docs/design/design-system.md) — every colour, font, type size, spacing step, radius, shadow and component.
- **Visual styleguide:** [`docs/design/design-system.html`](https://github.com/BanterbullOrg/banterbull-frontend/blob/main/docs/design/design-system.html) — open in a browser to see the tokens rendered.
- **Machine-readable tokens:** [`docs/design/tokens.json`](https://github.com/BanterbullOrg/banterbull-frontend/blob/main/docs/design/tokens.json) — a copy of which sits next to this file as [`tokens.json`](./tokens.json) for local tooling.
- **Source of truth in code:** `landing/index.html` (inline `<style>`) and `landing/new.css` in the frontend repo.

## Quick start — paste this `:root`

```css
:root{
  --accent:#FD5101; --accent-hover:#FF6A21;
  --yes:#0F766E; --no:#B91C1C; --no-bright:#FE3D33;
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

## The rules that matter most

- **One accent.** Orange `#FD5101` only, on the single most important element.
  Teal (`--yes` `#0F766E`) and red (`--no` `#B91C1C`) are **signals** (YES/NO,
  success/error), never decoration.
- **Never pure-black body text.** Body is `--fg-2`, captions `--fg-3`.
- **Separate surfaces with `--line` borders and `--bg-1` fills**, not grey
  blocks; reserve shadow for genuinely floating objects.
- **Headings: weight 300 + tight negative letter-spacing** — the brand's
  signature. Eyebrows/labels are mono, uppercase, letter-spaced.
- Light-only; no dark mode, no second accent, no new fonts, no emoji as UI
  markers.

For every exact value, read the canonical brand book linked above.
