# GEO Submission Skill Pack

This repository is a reusable example of how to prepare an NCBI GEO sequencing submission with Codex or Claude Code.

It has two purposes:

- show a real worked example of a GEO workbook being filled from manuscript and context files
- provide a reusable skill folder that other researchers can use on their own submissions

## Quick Start

For a new GEO submission project:

1. Copy `geo-submission-skill/` into a place where your coding agent can access skills.
2. Put your own GEO workbook, manuscript, and context files into a fresh working directory.
3. Ask Codex or Claude Code to review the directory and fill the workbook conservatively.
4. Verify sample-to-library mapping before accepting any bulk sample-row updates.
5. Finish the raw file, processed file, paired-end, and MD5 checksum sections manually or from a file inventory.

Recommended prompt:

```text
Use the GEO submission skill for this directory.
Review the manuscript, GEO workbook, sample sheet, and context files.
Fill the workbook only where the evidence is explicit.
If sample-row mapping is ambiguous, stop and explain the ambiguity before writing.
When done, summarize what still needs manual completion for GEO submission.
```

## Repository Contents

### Reusable skill

- `geo-submission-skill/`
  - reusable instructions for Codex or Claude Code
  - designed for GEO sequencing workbook completion
  - includes source-priority and workflow guidance

### Starter and reference files

- `seq_template_blank.xlsx`
  - clean GEO workbook starting point for a new study
- `context/GEO-updated.json`
  - generic field guide aligned to the GEO template, with shared SRA-derived controlled vocabulary
- `conversation.txt`
  - compact record of the decisions and edits made on the original worked example

The study-specific manuscript, filled workbook, sample sheet, and email correspondence used in the original worked example are not included in this repository because the underlying study is unpublished. `conversation.txt` records what was done and why.

## What This Example Demonstrates

`conversation.txt` walks through a real workflow in which the workbook was completed from:

1. a manuscript
2. an existing GEO workbook
3. a GEO context JSON
4. a researcher email summary
5. a FileMaker-style sample export for exact row mapping

The sample-level fields filled from those sources included:

- `title`
- `molecule`
- `instrument model`
- `description`
- `tissue`
- `genotype`

Shared study and protocol fields were also reviewed and completed where supported by the evidence.

## Recommended Input Set For Reuse

For best results, give the agent:

- a GEO workbook such as `seq_template_blank.xlsx`
- a manuscript in `.docx` or `.pdf`
- a concise email summary or curator Q&A dump
- a sample sheet or run export with exact sample ordering
- any structured metadata JSON that explains field expectations or controlled vocabulary

The sample sheet is usually the highest-confidence source for mapping sample names to workbook rows.

## Practical Workflow For Codex Or Claude Code

1. Inventory the directory.
2. Read the manuscript and context files.
3. Inspect the workbook to see what is already filled.
4. Identify the most authoritative source for sample ordering.
5. Fill study-level fields from the manuscript and curator-ready text.
6. Fill sample-level fields only where the source data is explicit.
7. Review the titles and descriptions as public-facing text.
8. Add file names and checksums after the upload set is finalized.

## Common Failure Modes

- Inferring sample order from genotype counts instead of using the actual sample export.
- Copying language from example tabs in the GEO workbook instead of the real study files.
- Trusting spreadsheet highlighting without checking the underlying values.
- Overfilling optional fields such as cell line, cell type, or treatment when the study does not support them.

## Sharing Model

This should live in git. The repository is the canonical, versioned source for:

- the reusable skill
- the worked example
- the prompt pattern
- future improvements from other researchers

The zip archive is for convenient handoff. The git repo is for maintenance and reuse.
