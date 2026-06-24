# Setup — References Folder

Run this before the brand guide orchestrator begins. It creates the references folder, tells the user what to put in it, and waits for confirmation.

---

## Step 1: Detect project structure

Check the project root for an existing `assets/` folder.

- If `assets/` exists → create `assets/references/`
- If no `assets/` → create `references/` at root

Store the resolved path. All subsequent references to "the references folder" mean this path.

---

## Step 2: Create subfolders

Inside the references folder, create:

```
references/
├── images/       ← logos, screenshots, photos, icons, mood board images
├── code/         ← HTML, CSS, JS, config files, snippets, component code
├── design/       ← Figma exports, PSDs, PDFs, style guides, mood boards
├── prompts/      ← AI prompts, content briefs, writing instructions
└── other/        ← anything that doesn't fit above
```

Add a `.gitkeep` in each subfolder so the structure is preserved in version control.

---

## Step 3: Output path and instructions

Send this to the user:

> "Your references folder has been created at: `[resolved path]`
>
> Drop anything you want referenced during brand guide generation into this folder. You can dump everything into the root — I'll sort it automatically — or place files directly into subfolders:
>
> - **images/** — logos, screenshots, photos, icons, mood board images (.png, .jpg, .svg, .webp, etc.)
> - **code/** — HTML, CSS, JS, config files, component snippets (.html, .css, .js, .ts, .json, .yaml, etc.)
> - **design/** — Figma exports, PSDs, PDFs, style guides, mood boards (.fig, .sketch, .psd, .pdf, .ai, etc.)
> - **prompts/** — AI prompts, content briefs, writing samples (.md, .txt containing prompt/instruction text)
> - **other/** — anything that doesn't clearly fit above
>
> Add your files and let me know when you're done."

---

## Step 4: Wait for confirmation

Do not proceed until the user confirms they've added their materials (or confirms they have nothing to add).

---

## Step 5: Organize dumped files

After the user confirms, scan the entire references folder recursively. For any files sitting in the root (not in a subfolder), classify and move them:

### Classification rules

**By extension (primary signal):**
- `images/` — `.png`, `.jpg`, `.jpeg`, `.gif`, `.svg`, `.webp`, `.ico`, `.bmp`, `.tiff`, `.avif`
- `code/` — `.html`, `.css`, `.scss`, `.js`, `.ts`, `.jsx`, `.tsx`, `.json`, `.yaml`, `.yml`, `.xml`, `.py`, `.sh`, `.env`, any `.config.*`
- `design/` — `.fig`, `.sketch`, `.xd`, `.psd`, `.ai`, `.pdf`, `.eps`

**By content (for ambiguous extensions like `.md`, `.txt`):**
- Read the file content
- If it contains prompt text, AI instructions, system prompts, or content briefs → `prompts/`
- If it contains design specs, style descriptions, or visual direction → `design/`
- If it contains code documentation or technical specs → `code/`
- If unclear → `other/`

**Ambiguous or unclassifiable files:**
- List them and ask the user where they should go before moving

### After sorting

Output a summary table:

| File | Moved to | Reason |
|------|----------|--------|
| logo.png | images/ | Image file (.png) |
| styles.css | code/ | Code file (.css) |
| brief.md | prompts/ | Contains content brief text |

---

## What this script never does
- Deletes any user files
- Renames files (only moves them into subfolders)
- Proceeds without user confirmation
- Guesses on ambiguous files without asking
