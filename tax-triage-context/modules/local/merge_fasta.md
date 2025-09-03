# MERGE_FASTA Module

## Big Picture
The `MERGE_FASTA` module merges multiple FASTA files into a single FASTA file for downstream analysis or reporting.

## Process Name
`MERGE_FASTA`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(fastas)`: Metadata and FASTA files to be merged.

## Outputs
- `tuple val(meta), path("*merged.fasta")` (emit: fasta): Merged FASTA file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `merge_fasta.sh` from the pipeline's `bin/` directory to merge FASTA files.

## Script Section Explanation
- Runs `merge_fasta.sh` with the provided FASTA files and sample base name.
- Captures gawk version information in `versions.yml`.

---

# Example Command
```
bash merge_fasta.sh -i <fastas> -s <sample_base> -o <output.fasta>
```
