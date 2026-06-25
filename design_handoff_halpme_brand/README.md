# halpme — Brand & Design System Handoff

This bundle is the portable, machine-readable version of the halpme brand system.
Drop it into your repo (e.g. `halpme-sh/halpme` or the website repo) and point
Claude Code — or any developer — at it to build **halpme.sh** on-brand.

> **What halpme is:** a zsh CLI that renders your own Markdown notes (aliases,
> workflows, tool configs) as terminal help. Tagline: *"Terminal help for your setup."*

---

## What's in here

| File | Purpose |
|------|---------|
| `BRAND.md` | The human-readable rulebook: logo usage, color roles, type, voice, components, do/don'ts. **Read this first.** |
| `design-tokens.css` | CSS custom properties (`--accent`, `--ink`, `--paper`, type, spacing, radii, shadows). The source of truth for styling. |
| `tokens.json` | Same tokens as structured JSON, for build tools / Tailwind config / Style Dictionary. |
| `fonts.css` | `@font-face` + import snippet for **Monaspace Neon** (mono) and **Hanken Grotesk** (sans). |
| `hero.html` | A self-contained, framework-free reference build of the hero + terminal demo. Open it in a browser; use it as the concrete starting component. |
| `Halpme Brand System.dc.html` | The full visual guidelines page (the original reference). Note: this is built for a specific design tool and **won't render in a plain browser** — keep it as the canonical visual reference / for screenshots. |

---

## How to use it with Claude Code

1. Commit this folder into your repo.
2. In Claude Code, give it a prompt like the one below. It will read `BRAND.md`
   and `design-tokens.css` and stay on-system.

### Copy-paste starter prompt

```
Build the halpme.sh landing page.

halpme is a zsh CLI: "Terminal help for your setup" — it renders your own
Markdown notes (aliases, workflows, tool configs) as terminal help.

Follow the brand system in design_handoff_halpme_brand/:
- Read BRAND.md for logo usage, color roles, typography, voice, and components.
- Use design-tokens.css (or tokens.json) for ALL colors, fonts, spacing, radii.
  Do not invent new colors or fonts.
- Load fonts via fonts.css (Monaspace Neon for mono/brand, Hanken Grotesk for prose).
- Use hero.html as the reference for the hero section + terminal demo, then
  recreate it in [React + Tailwind / Astro / plain HTML — your stack here].

Stack: [state your framework]. Match the reference pixel-for-pixel where shown,
and extend the same system for any new sections.
```

3. For anything not covered, tell it to follow the spirit of `BRAND.md`
   (warm, plain, lowercase, terminal-native).

---

## Notes & caveats

- **The `.dc.html` file is a design reference, not production code.** The portable,
  implementable parts are `design-tokens.css`, `tokens.json`, `fonts.css`,
  `BRAND.md`, and `hero.html`.
- **Fonts:** `fonts.css` loads Monaspace Neon from the Fontsource CDN and Hanken
  Grotesk + Space Grotesk from Google Fonts. For production, self-host the woff2
  files (see comments in `fonts.css`) so the site has no third-party font dependency.
- We use the **standard** Monaspace Neon webfont, not the Nerd Font (NF) build —
  the NF glyphs are terminal icons not needed for web text.
- Colors are defined in both hex and oklch in the token files; oklch is the
  authoring source (coral and teal share the same lightness/chroma, hue only differs).
