# MERGEDSUBSPECIES Module

## Big Picture
The `MERGEDSUBSPECIES` module merges subspecies classification results across samples, producing a complete merged hierarchy CSV and individual hierarchy CSVs for downstream analysis.

## Process Name
`MERGEDSUBSPECIES`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `file(reports)`: Subspecies report files to be merged.
- `file(pathogens)`: Pathogens file for filtering.

## Outputs
- `path("*complete.krakenreport.merged.hierarchy.csv")` (emit: mergedhierarchy): Merged hierarchy CSV.
- `path("*.single.csv")` (emit: individualhierarchy): Individual hierarchy CSVs (optional).

## Use of bin Scripts
- Uses `merge_subspecies.py` from the pipeline's `bin/` directory to merge subspecies results.

## Script Section Explanation
- Runs `merge_subspecies.py` with the provided reports and pathogens file.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
merge_subspecies.py -o complete.krakenreport.merged.hierarchy.csv -i <reports> -e S -p <pathogens>
```
