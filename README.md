# Brand Guide

A Claude Code skill that builds a complete brand guide from your inputs. It orchestrates three sub-skills in sequence — positioning, voice, and design — to produce a set of markdown files that define your brand.

## What it produces

- **Brand Positioning** — who you're for, what you stand against, your POV, your mechanism
- **Brand Voice** — vocabulary, rhythm, structure, and tone rules applied to all content
- **Brand Design** — color palette, typography, and design style specs

All outputs land in `assets/content/brand-guide/` by default. See [output-reference.md](output-reference.md) for the full file list and schema.

## Prerequisites

You need three things before running:

1. **Brand Identity / Dogma doc** — [fill in template](https://docs.google.com/document/d/1c58fHY5ejxsKdUMIoXcspMvpw-MtZK3TOg_51lMFUkA/edit?tab=t.0)
2. **Brand Voice skill** — [download](https://github.com/hangyibaite/brand-voice-skill)
3. **Brand Palette doc** — [fill in template](https://docs.google.com/document/d/1i5btsk2Cjsvcme-ebvni80q_Nw-S7ZYWWV7XZvZ_w1g/edit?tab=t.0)

**Strongly recommended** (significantly improves output quality):

4. **ICP output** — run the [ICP Personaliser](https://github.com/hangyibaite/ICP-personaliser) skill first
5. **Offer Breakdown output** — run the [Offer Breakdown](https://github.com/hangyibaite/offer-breakdown) skill first

## Usage

1. Add this skill to your Claude Code project
2. Say "build my brand guide" or any brand-related trigger
3. Attach your documents when prompted
4. Confirm each output before the next step runs

The skill will never skip inputs, run out of order, or generate content without your confirmation.

## Structure

```
brand-guide/
├── SKILL.md                          # Orchestrator
├── output-reference.md               # Output file list and schema
├── README.md
└── sub-skills/
    ├── brand-positioning.md          # Positioning generation
    ├── brand-voice.md                # Voice rules and content generation
    └── brand-design.md              # Color, typography, design style
```

## Version

v1.2
