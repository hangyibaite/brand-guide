# Sub-skill: Brand Positioning

Generates `brand-positioning.md` from three inputs: dogma doc, ICP, and offer breakdown. All three improve output quality. Dogma doc is required. ICP and offer can be submitted as generated skill outputs or pasted as text.

---

## Input check

On launch, always send this prompt:

---

> "To build your brand positioning I need up to 3 inputs. The more you provide, the sharper the output.
>
> **1. Brand Identity/Dogma doc** (required)
> Your filled brand identity document.
> → Don't have one? It was already submitted in Phase 1. If you skipped it, go back and fill it in: https://docs.google.com/document/d/1c58fHY5ejxsKdUMIoXcspMvpw-MtZK3TOg_51lMFUkA/edit?tab=t.0
>
> **2. ICP (Ideal Client Profile)** (strongly recommended)
> The output from the ICP Personaliser skill — either attach the generated file or paste the text.
> → Haven't built your ICP yet? Download the skill and run it first: https://github.com/hangyibaite/ICP-personaliser
>
> **3. Offer Breakdown** (strongly recommended)
> The output from the Offer Breakdown skill — either attach the generated file or paste the text.
> → Haven't built your offer breakdown yet? Download the skill and run it first: https://github.com/hangyibaite/offer-breakdown
>
> Attach or paste whatever you have. If you only have the dogma doc, we can still proceed — but ICP and offer will make your positioning significantly more specific."

---

**Reference materials:** Also scan the references folder (check `references/` or `assets/references/`) for any materials relevant to positioning — competitor screenshots, market docs, positioning examples, content samples. Note which references you find; they will be cited in the output.

If dogma doc is missing after they respond: stop, tell them it's required, send the link again.
If ICP or offer are missing: proceed but flag at the end which sections are weaker as a result and recommend they rerun after completing those skills.

---

## Extraction: map inputs to six output sections

Read all attached documents. Use the user's own language wherever possible. This file should sound like them, not like a brand consultant.

### 1. The Gap We Occupy
Source: dogma doc (industry belief system, what pisses them off) + offer breakdown (what the offer is not)

Write what the brand is NOT first — negative space before positive. Positioning is always relative. Pull specific language they used to describe what's broken in their industry. Then state what it is.

### 2. The Person We're For
Source: ICP output (primary) + dogma doc "who you're building for" (secondary)

Extract: who they are as a person (not demographics), the worldview they already hold, what annoys the user about them, and who is explicitly NOT the client. If ICP output exists, use its specificity — it will be more detailed than the dogma doc alone. The worldview item is the most critical: positioning aligns with an existing belief, it never installs a new one.

### 3. Point of View — Things We Say That Others Won't
Source: dogma doc (universal + industry belief systems)

Extract 4–6 beliefs the user holds that most people in their space won't say publicly. Format: bold one-line claim, then 2–3 sentences of explanation in their voice. Do not soften. These should feel slightly uncomfortable to a competitor reading them.

### 4. The Proprietary Mechanism
Source: offer breakdown (primary) + dogma doc (secondary)

Extract the named method or system that produces the outcome. If it has a name, use it. Describe its components specifically using the offer breakdown's language. If unnamed, flag it: "Your mechanism doesn't have a name yet — name it before this file is finalised. Unnamed mechanisms don't convert."

### 5. Positioning Statement (Internal Use Only)
Synthesise from all sections above.

Format: "For [specific person] who [specific situation], [name/brand] is [what it actually is] that [produces what outcome]. Unlike [category default], we [the specific differentiator]."

Label clearly as internal — not for public use. It's the compass every piece of content gets checked against.

If ICP or offer are missing, this statement will be less specific. Flag it: "This statement will sharpen significantly once you run the ICP Personaliser and Offer Breakdown skills."

### 6. What We Never Say
Source: dogma doc (industry beliefs + identity/vocabulary signals) + offer breakdown (what the offer is not)

List specific phrases, framings, and language the brand refuses. Concrete terms only — not "avoid jargon" but the actual jargon words to ban. Pull any language explicitly called out as broken, dishonest, or off-brand.

---

## Output format

Write `brand-positioning.md` in clean markdown. H2 headers matching the six section names above. Prose within sections — no bullet dumps unless the content genuinely requires a list. Under 600 words total. Dense, not exhaustive.

End the file with a `## References` section listing which reference files were consulted and what section or decision each one informed. If no reference materials were used, omit this section.

---

## What this sub-skill never does
- Proceeds without the dogma doc
- Invents anything not present in the attached documents
- Softens strong beliefs to sound more palatable
- Produces generic positioning language ("we believe in quality and results")
- Treats missing ICP or offer as a blocker — flags the gap and proceeds
