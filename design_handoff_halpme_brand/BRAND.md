# halpme — Brand Guidelines

**Terminal help for your setup.**
halpme is a zsh CLI that renders your own Markdown notes — aliases, workflows, tool
configs — as searchable terminal help. It's open source (MIT) and installs via a
Claude Code skill (`npx skills add halpme-sh/halpme`).

This document is the rulebook. Values live in `design-tokens.css` / `tokens.json`.

---

## 1. Personality

Clean, confident developer tool with a friendly wink. The name is a meme-y "halp
me" — the *writing* stays straight and useful. Terminal-native, lowercase, warm.
Not a joke, not corporate.

---

## 2. Logo

The mark is a **live prompt**: the wordmark set in monospace, ending in a blinking
block cursor. The tool is always at the prompt, waiting to halp.

### Construction
- Wordmark: `halpme`, **lowercase**, `Monaspace Neon` **700**, tracking `-0.04em`.
- Prompt chevron `❯` (U+276F) in **coral**, sits to the left with ~0.25em gap.
- Block cursor: a coral rectangle after the final "e" — width `0.5em`, height `1em`,
  radius `2px`, blinking `1.1s steps(1,end) infinite` (`@keyframes hm-blink`).
- Full lockup: `❯ halpme▮`

### Variants
- **Primary** — `❯ halpme▮` on paper.
- **Wordmark only** — `halpme` (no chevron/cursor) for tight spaces.
- **Reversed** — same lockup on `--ink`; cursor stays coral.
- **On accent** — on coral; chevron at 70% opacity, cursor becomes paper.
- **App icon** — `--ink` rounded square (radius `24px` @ 96px), containing a coral
  `❯` + a paper block cursor, centered.

### Clear space & sizing
- Keep clear space ≥ the cursor's width on all sides.
- Minimum wordmark size: 16px (nav). Below that, use the app icon.

### Do
- Lowercase, monospace, cursor in coral.
- Let the cursor blink in live/interactive contexts; static is fine in print.

### Don't
- ❌ Capitalize ("Halpme", "HALPME") or set in a sans.
- ❌ Stretch, condense, skew, or rotate.
- ❌ Add shadows, glows, outlines, or gradients.
- ❌ Recolor the cursor to anything but coral (or paper on coral).

---

## 3. Color

Warm, low-saturation base for comfortable long-form docs. Two signal colors only.

| Token | Hex | Role |
|-------|-----|------|
| `--accent` (coral) | `#E0654A` | Brand voice, primary buttons, prompts, topic names |
| `--accent-2` (teal) | `#1F9E86` | Keywords, matched terms, success |
| `--ink` | `#211E1B` | Body text, dark surfaces |
| `--paper` | `#F6F1E9` | Page background |
| `--paper-raised` | `#FCFAF5` | Cards |
| `--border` | `#E4DCCF` | Hairlines |
| `--muted` | `#6E665C` | Secondary text |

- Coral and teal share the same lightness/chroma in oklch — only hue changes.
- For **text on light**, use the `-strong` variants (`#C9512F`, `#177A68`) for contrast.
- Never pure `#000` or `#FFF`. Body text = `--ink` (900); secondary = `--muted` (500).
- **Terminal surfaces** are dark (`--term-bg #1B1916`) and mirror the brand: coral
  prompts, teal matches, warm-gray chrome (`--term-dim #7E776B`).

---

## 4. Typography

Two families, clear roles.

- **Hanken Grotesk** (`--font-sans`) — headings + body + UI prose. Weights 400–800.
- **Monaspace Neon** (`--font-mono`) — the wordmark, all code, terminal output,
  eyebrow labels, and chips. Weights 400/500/700.
- *(Optional)* **Space Grotesk** — alternate display face for big headlines.

### Scale
| Style | Size | Font / weight | Notes |
|-------|------|---------------|-------|
| Wordmark | 64 | mono 700 | tracking -0.04em |
| Display | 48 | sans 700 | tracking -0.03em, lh 1.1 |
| H2 | 34 | sans 700 | tracking -0.02em |
| H3 | 21 | sans 600 | |
| Body | 16 | sans 400 | lh 1.6 |
| Small | 14 | sans 400 | |
| Code/caption | 13 | mono 400 | lh 1.7 |
| Label/eyebrow | 11 | mono 500 | UPPERCASE, tracking 0.12–0.16em, often coral |

- Headlines are lowercase or sentence case — calm, never shouty.
- Eyebrow labels are numbered + mono: `01 — IDENTITY`.

---

## 5. Components

All measurements in `design-tokens.css`.

- **Buttons** — Primary: coral fill, paper text, radius 9, padding 11×20, weight 600.
  Secondary: transparent + 1px `#C9BFAE` border. Ghost: text + coral `→`.
- **Command block** — dark (`--term-bg`) rounded 10; coral `$` prompt; mono;
  optional titlebar + copy affordance. The signature CTA.
- **Keyword chips** — mono 13, radius 7. Coral tint (`#FBEAE5`/`#C9512F`) or teal
  tint (`#E4F4EE`/`#177A68`). Used for topic names (`git`, `brew`).
- **Badges/pills** — mono 11.5, radius 20; solid ink or 1px-border outline.
- **Cards** — `--paper-raised`, 1px `--border`, radius 14, generous padding (20–46).
- **Callout** — paper card with a 3px coral left border + coral `❯`.
- **Terminal window** — radius 13, 1px `--term-border`, titlebar with red/yellow/green
  dots + path label, `--shadow-term`. Output uses coral prompts and teal keywords.
- **Links** — coral, underline, offset 3px, thickness 1.5px. Inline code = mono on
  `--n-100` chip.

---

## 6. Voice & tone

Friendly, plain, never precious. Short sentences. Verbs first. We help, we don't lecture.

**Principles**
- *Plain over clever* — say what it does; save jokes for the name and the 404.
- *Yours, not ours* — it's the user's setup, their words. Never call notes "content."
- *Lowercase calm* — match the prompt; no exclamation pile-ups.

**We say**
- "Terminal help for your setup."
- "Add a file, add a section — it just shows up."
- "Forgot your own alias? halpme git."

**We don't**
- ~~"The ultimate AI-powered knowledge platform."~~
- ~~"Revolutionize your developer experience!!"~~
- ~~"Leverage synergistic documentation."~~

---

## 7. Iconography

Keep it minimal and terminal-native. Prefer typographic glyphs over drawn icons:
the chevron `❯`, `$` prompt, `_`/`▮` cursor, `→` for flow. If icons are needed, use a
thin monoline set that visually matches Monaspace's weight; never heavy/filled.
