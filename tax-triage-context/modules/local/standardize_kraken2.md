# STANDARDISE_KRAKEN2 Module

## Big Picture
The `STANDARDISE_KRAKEN2` module standardizes Kraken2 report files by extracting specific columns, producing a simplified report for downstream analysis.

## Process Name
`STANDARDISE_KRAKEN2`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gnu-wget:1.18--0`
  - Docker: `biocontainers/gnu-wget:1.18--h36e9172_9`

## Inputs
- `tuple val(meta), val(REPORT)`: Metadata and Kraken2 report file.

## Outputs
- `path("*report")` (emit: report): Standardized report file.

## Use of bin Scripts
- Uses shell commands to extract columns; no custom bin script.

## Script Section Explanation
- Uses `cut` to extract columns 2 and 5 from the Kraken2 report, outputs standardized report.

---

# Example Command
```
cut -d $'\t' -f 2,5 <REPORT> > <sample_id>.standardized_report.txt
```
