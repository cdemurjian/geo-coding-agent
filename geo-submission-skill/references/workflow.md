# Workflow Details

## Study-level metadata

Pull these from the manuscript abstract, methods, and curator email summaries:

- study title
- summary
- experimental design
- contributors

Use the manuscript for scientific framing and the email chain for curator-facing wording when it is more submission-ready.

## Sample-level metadata

For each row:

1. identify the library name already present in the workbook
2. map it to the sample name from the sample sheet
3. convert the sample name into a GEO-friendly title
4. fill genotype using exact allele notation when available
5. fill tissue, molecule, layout, and instrument from the strongest common evidence
6. write a short description that captures organism material, stage, and replicate identity

## Raw and processed files

Usually defer these until the end because they depend on the final upload set.

Before completion, make sure:

- raw files match the `single` or `paired` value
- paired-end rows are listed in the paired-end experiments table if required by the workbook
- all processed files referenced in the sample table exist in the upload bundle
- MD5 checksums are present for every uploaded raw and processed file

## Warnings

- GEO templates may contain noisy conditional formatting.
- Workbook examples are illustrative only; do not copy irrelevant fields from example sheets.
- Do not fabricate cell line, cell type, or treatment values when the study is whole-organism and untreated.
