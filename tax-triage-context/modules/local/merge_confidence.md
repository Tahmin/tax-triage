# MERGE_ALIGNMENT_MERGES Module

## Big Picture
The `MERGE_ALIGNMENT_MERGES` module merges multiple metrics files into a single MultiQC-compatible TSV report for downstream analysis.

## Process Name
`MERGE_ALIGNMENT_MERGES`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `file metrics`: Metrics file(s) to be merged.

## Outputs
- `path("*metrics*.merged_mqc.tsv")` (emit: metrics_report): Merged metrics report.

## Use of bin Scripts
- Uses `merge_tsvs.py` from the pipeline's `bin/` directory to merge metrics files.

## Script Section Explanation
- Runs `merge_tsvs.py` to generate the merged metrics report.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
merge_tsvs.py -o metrics.merged_mqc.tsv -i <metrics>
```
