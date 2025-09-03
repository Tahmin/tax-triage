# RUN_BLAST_REMOTE Module

## Big Picture
The `RUN_BLAST_REMOTE` module runs BLAST searches remotely using a custom Python script, producing tabular results for downstream analysis.

## Process Name
`RUN_BLAST_REMOTE`

## Container/Conda Environment
- **Conda:** `bioconda::blast=2.12.0` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/blast:2.12.0--pl5262h3289130_0`
  - Docker: `biocontainers/blast:2.12.0--pl5262h3289130_0`

## Inputs
- `tuple val(meta), path(assembly)`: Metadata and assembly file to be queried.

## Outputs
- `tuple val(meta), path("*blast.txt")` (emit: txt): BLAST tabular results.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `run_blast.py` from the pipeline's `bin/` directory to run BLAST remotely.

## Script Section Explanation
- Runs `run_blast.py` with the assembly file and output filename.
- Captures BLAST version information in `versions.yml`.

---

# Example Command
```
run_blast.py <assembly> <output.txt>
```
