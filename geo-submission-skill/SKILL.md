---
name: geo-submission-skill
description: Use this skill when preparing or partially automating an NCBI GEO sequencing submission from a manuscript, GEO seq_template workbook, sample sheet, and supporting context files such as curator email summaries or metadata JSON guides.
---

# GEO Submission Skill

Use this skill to fill a GEO sequencing submission workbook from local evidence. Prefer conservative extraction over guessing.

## Inputs To Look For

Look for these files first:

- a GEO workbook such as `seq_template.xlsx`
- a manuscript in `.docx` or `.pdf`
- `context/` files with email summaries or metadata JSON
- a sample sheet, FileMaker export, or instrument export

If a sample sheet exists, treat it as the strongest source for row-to-library mapping.

Read [references/input-priority.md](references/input-priority.md) before filling sample rows.

## Workflow

1. Inventory the directory and identify the manuscript, workbook, context files, and sample sheet.
2. Extract study-level metadata from manuscript and email/context sources.
3. Inspect the workbook to see what is already filled.
4. Build a row-to-sample mapping from the strongest available source.
5. Fill only fields supported by evidence.
6. Leave unsupported fields blank and tell the user exactly what is still missing.

Read [references/workflow.md](references/workflow.md) for field-level guidance.

## Rules

- Do not infer sample ordering from genotype counts alone if a sample sheet exists.
- Prefer exact controlled vocabulary where the template or context file provides one.
- Keep public-facing sample titles descriptive but consistent with the sample sheet.
- Preserve a backup workbook before bulk edits.
- When spreadsheet highlighting suggests duplicates, verify actual values instead of trusting formatting alone.

## Typical Fields To Fill

Common sample-level fields:

- `*title`
- `*library strategy`
- `*organism`
- `**tissue`
- `genotype`
- `*molecule`
- `*single or paired-end`
- `*instrument model`
- `description`

Common protocol fields:

- `growth protocol`
- `treatment protocol`
- `*extract protocol`
- `*library construction protocol`
- `*data processing step`

## Final Review

Before calling the workbook ready:

- verify sample titles and genotypes against the sample sheet
- confirm all library names are unique
- confirm layout and instrument match the manuscript or sequencing summary
- identify remaining manual tasks such as raw files, processed files, and MD5 checksums
