# REFERENCE_REHEADER Module

## Big Picture
The `REFERENCE_REHEADER` module reformats FASTA headers for reference sequences, producing a standardized FASTA file for downstream analysis.

## Process Name
`REFERENCE_REHEADER`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(fasta)`: Metadata and FASTA file to be reformatted.

## Outputs
- `tuple val(meta), path("*.reformat.fasta")` (emit: fasta): Reformatted FASTA file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `reheader_fasta.sh` from the pipeline's `bin/` directory to reformat FASTA headers.

## Script Section Explanation
- Runs `reheader_fasta.sh` with the provided FASTA file and arguments.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
reheader_fasta.sh -i <fasta> -o <output.fasta> <args>
```
