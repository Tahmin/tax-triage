# MERGEDKRAKENREPORT Module

## Big Picture
The `MERGEDKRAKENREPORT` module merges multiple Kraken report files into a single MultiQC-compatible TSV report for downstream analysis.

## Process Name
`MERGEDKRAKENREPORT`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `file reports`: Kraken report files to be merged.

## Outputs
- `path("*krakenreport*.merged_mqc.tsv")` (emit: krakenreport): Merged Kraken report.

## Use of bin Scripts
- Uses `merge_tsvs.py` from the pipeline's `bin/` directory to merge Kraken report files.

## Script Section Explanation
- Runs `merge_tsvs.py` to generate the merged Kraken report.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
merge_tsvs.py -o krakenreport.merged_mqc.tsv -i <reports>
```
