# Sub-skill: Brand Design

Generates `color-palette.md`, `typography.md`, and `design-style.md` from the user's filled brand palette document. Reads `brand-positioning.md` first — every design decision must be grounded in positioning, not preference alone.

---

## Input check

Has the user attached a filled brand palette document?

If not, send them here and stop:

> "Fill in your brand palette template before we continue. Go here: https://docs.google.com/document/d/1i5btsk2Cjsvcme-ebvni80q_Nw-S7ZYWWV7XZvZ_w1g/edit?tab=t.0
>
> Watch the 'Claude Can't Fix Ugly' lesson first if you haven't. Attach the filled doc when you're done."

Do not proceed until attached.

---

## Step 1: Read before generating

Read in this order:
1. `brand-positioning.md` — extract personality axes, what the brand is not, named competitors
2. Attached brand palette doc — extract all filled values
3. Reference materials in the references folder (check `references/` or `assets/references/`) — scan `images/`, `code/`, `design/`, and `other/` subfolders

Every design decision below must trace back to one of these three sources.

---

## Step 2: Generate `color-palette.md`

### Non-negotiables (apply always, no user input needed)
- 60-30-10 rule: primary neutral 60%, secondary brand color 30%, accent 10%
- Never pure black (#000000) or pure white (#FFFFFF) — use near-black and off-white
- Minimum contrast ratio 4.5:1 for body text (WCAG AA)
- Never more than 3 brand colors + neutrals

### Extract from palette doc
For each color, output: name, HEX, HSL, one sentence on what job it does

- **Primary** — the color the brand is remembered by
- **Secondary** — supports and grounds the primary
- **Accent** — used sparingly, creates contrast
- **Neutrals** (2–3) — near-black, off-white, one mid-tone
- **Tints/shades** — 3 variants each for primary and secondary (for hover states, backgrounds, borders)
- **Dark mode variants** — if specified in palette doc

Also extract: brand color psychology note (what each color is meant to signal).

State 60-30-10 application explicitly in the file.

---

## Step 3: Generate `typography.md`

### Non-negotiables (apply always)
- Max 2–3 typefaces
- Scale: each font level × 1.625rem (adjustable based on font)
- Line height — paragraphs: 1.35–1.6 / H1–H3: 0.85–1.2
- Kerning — tight for display, normal for body
- Never full justify (JAWS — Justified Atrocity Wall of Suffering)
- Paragraph max-width: 60–100ch
- Never more than 2 font weights per typeface in a single layout
- No decorative fonts for body text
- Always specify `-webkit-font-smoothing: antialiased`

### Extract from palette doc
- **Display font** — name, source (Google Fonts / paid), license note, weight used
- **Body font** — name, source, license note, weight used
- **Monospace font** — if specified (code blocks, data display)
- **Pairing rationale** — one sentence on why these work together (contrast principle: serif display + sans body, never two serifs)
- **Fallback font stack** — what renders if the primary font fails

### Size scale (output in file)
| Level | REM | Line Height | Kerning |
|-------|-----|-------------|---------|
| Display | 4.236rem | 0.85–1.0 | tight |
| H1 | 2.618rem | 0.9–1.1 | tight |
| H2 | 1.618rem | 1.0–1.2 | slight |
| H3 | 1.0rem | 1.1–1.2 | normal |
| Body | 1.0rem base | 1.35–1.6 | normal |
| Label/UI | 0.618rem | 1.2–1.35 | wide |

Note: adjust multipliers based on the specific font — some typefaces run large or small.

---

## Step 4: Generate `design-style.md`

### Non-negotiables (apply always)
- Single icon style throughout — flat, outlined, or filled. Never mixed.
- Consistent imagery treatment — all photos or all illustrations, never mixed unless specified

### Extract from palette doc

**Shape language**
- Border radius value from palette doc
- Derive from positioning: approachable → rounded, precise/premium → sharp

**Spacing**
- Base unit: 8px grid (non-negotiable)
- Extract minimum padding rules per section from palette doc

**Imagery/photography**
- Real photos / illustration / none
- If photos: color grading rules, overlay treatment
- If illustration: style (flat, outlined, filled)

**Shadow and border**
- Shadow style and specific box-shadow values if specified
- Border style and px values if specified

**Texture**
- Yes or no. If yes, opacity range.

**Motion/animation**
- Bouncy / smooth / none
- Transition duration range
- Easing preference

**Button style**
- Pill / rounded / sharp + padding spec from palette doc

**What never appears**
- Visual equivalent of "what we never say" from positioning
- Specific patterns, color combos, or treatments that are off-brand

### Brand personality axes (extract from palette doc, use to QC every decision above)
- Warm ↔ Cool
- Playful ↔ Serious
- Minimal ↔ Expressive
- Editorial ↔ Functional

Every spec in this file should be consistent with where the brand sits on these axes. Flag any conflict before writing the file.

---

## Step 5: Reference materials

After generating all three files, check the references folder (check `references/` or `assets/references/`):

- `images/` — note which references informed which decisions in each file
- `code/` — note which snippets correspond to which specs
- `design/` — note which design files informed which style decisions
- `prompts/` — note any briefs that shaped direction
- `other/` — note anything else that was used

Add a `## References` section at the bottom of each file listing which reference materials were used and what decision each one informed.

---

## Output files
- `color-palette.md`
- `typography.md`
- `design-style.md`

Default path: `assets/content/brand-guide/` — can be changed by telling Claude Code a different path before running.

Show each file to the user and confirm before moving to the next.

---

## What this sub-skill never does
- Makes design decisions without reading `brand-positioning.md` first
- Skips the brand palette doc check
- Uses preference as justification ("this looks nice") without a positioning rationale
- Invents values not present in the palette doc or references
- Mixes icon styles
- Uses pure black or pure white
