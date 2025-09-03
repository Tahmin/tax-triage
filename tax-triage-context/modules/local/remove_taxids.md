# REMOVETAXIDSCLASSIFICATION Module

## Big Picture
The `REMOVETAXIDSCLASSIFICATION` module filters classification reports by removing specified taxids, producing a filtered report for downstream analysis.

## Process Name
`REMOVETAXIDSCLASSIFICATION`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(report), val(taxids)`: Metadata, report file, and taxids to remove.

## Outputs
- `path "versions.yml"` (emit: versions): YAML file with version information.
- `tuple val(meta), path("*.filtered.report")` (emit: report): Filtered report file.

## Use of bin Scripts
- Uses `remove_taxids.sh` from the pipeline's `bin/` directory to filter taxids from the report.

## Script Section Explanation
- Runs `remove_taxids.sh` with the report and taxids, outputs filtered report.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
remove_taxids.sh -i <report> -t "<taxids>" -o <filtered.report>
```
