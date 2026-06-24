---
name: brand-guide
description: >
  Build a complete brand guide. Triggers on "build my brand guide", "brand positioning", "brand palette", "visual identity", "brand voice", or any request to define positioning, design, or voice. Orchestrates three sub-skills in sequence. Always call this skill instead of sub-skills individually.
---

# Brand Guide — Orchestrator

## Phase 0: Setup

On launch, read and execute `setup.md` first. This creates the references folder (at `references/` or `assets/references/` depending on the project structure), outputs the path to the user, and waits for them to add reference materials before continuing.

Do not proceed to Phase 1 until setup is complete.

---

## Phase 1: Input collection

On launch, always send this prompt first — regardless of what the user has or hasn't attached:

---

> "Before we build your brand guide, I need 3 required documents and 2 optional but strongly recommended ones. Attach everything you have to this chat.
>
> **Required:**
>
> **1. Brand Identity/Dogma doc**
> Your filled brand identity document — beliefs, personality, who you're building for, what you want.
> → Don't have one? Fill it in here: https://docs.google.com/document/d/1c58fHY5ejxsKdUMIoXcspMvpw-MtZK3TOg_51lMFUkA/edit?tab=t.0
> → Watch the **Brand Positioning** lesson first.
>
> **2. Brand Voice skill**
> The personalised voice skill built from your content.
> → Don't have one? Download the skill here: https://github.com/hangyibaite/brand-voice-skill
> → Watch the **Brand Voice** lesson first.
>
> **3. Brand Palette doc**
> Your filled brand palette — colors, typography, design style specs.
> → Don't have one? Fill it in here: https://docs.google.com/document/d/1i5btsk2Cjsvcme-ebvni80q_Nw-S7ZYWWV7XZvZ_w1g/edit?tab=t.0
> → Watch the **Claude Can't Fix Ugly** lesson first.
>
> **Strongly recommended (improves positioning quality significantly):**
>
> **4. ICP (Ideal Client Profile)**
> The output from the ICP Personaliser skill — attach the file or paste the text.
> → Don't have one? Run this skill first: https://github.com/hangyibaite/ICP-personaliser
>
> **5. Offer Breakdown**
> The output from the Offer Breakdown skill — attach the file or paste the text.
> → Don't have one? Run this skill first: https://github.com/hangyibaite/offer-breakdown
>
> If you haven't already, drop any reference materials into the references folder created during setup — the path was shown above. Screenshots, images, code snippets, design files, prompts, anything relevant. I'll organize them automatically.
>
> Attach everything and I'll get started."

---

Wait for the user to respond. If any of the 3 required docs are missing, list exactly which ones and stop. Do not proceed until all 3 required docs are confirmed. Missing ICP or offer — proceed but flag the gap.

---

## Phase 2: Clarifying questions

Read all attached documents. Ask any clarifying questions. Present a brief summary of understanding. User confirms before any file is written.

---

## Phase 2.5: Organize References

Before running sub-skills, scan the references folder and organize any unsorted files. Follow the classification and sorting rules in `setup.md` Step 5. Output a summary of what was found and where it was placed. Flag any ambiguous files for user confirmation.

This organized structure is now available to all sub-skills during Phase 3.

---

## Phase 3: Sub-skill execution

Run sequentially. User confirms each output before moving to the next.

**1. Brand Positioning**
Read `sub-skills/brand-positioning.md` and execute in full.
Output: `brand-positioning.md`

**2. Brand Voice**
Read `sub-skills/brand-voice.md` and execute in full.
Output: `brand-voice.md`

**3. Brand Design**
Read `sub-skills/brand-design.md` and execute in full.
Reads `brand-positioning.md` before generating anything.
Outputs: `color-palette.md`, `typography.md`, `design-style.md`

---

## Phase 4: Done

Default output path: `assets/content/brand-guide/` — created automatically.
To change the path, tell Claude Code before running this skill.

> "Your brand guide is complete. Everything downstream — landing page, copy, content — reads from your brand guide folder. Your references are organized at `[references path]`. Make sure your CLAUDE.md points to both the brand guide output folder and the references folder."

---

## What this skill never does
- Skips the Phase 1 prompt — it always fires on launch
- Proceeds with any of the 3 required docs missing
- Runs sub-skills out of order or in parallel
- Generates content itself — all generation is delegated to sub-skills
- Changes between users — only the outputs differ
