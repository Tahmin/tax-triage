# REMOTE_BLASTN Module

## Big Picture
The `REMOTE_BLASTN` module performs remote BLASTN searches against a specified database, producing tabular results for downstream analysis.

## Process Name
`REMOTE_BLASTN`

## Container/Conda Environment
- **Conda:** `bioconda::blast=2.12.0` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/blast:2.12.0--pl5262h3289130_0`
  - Docker: `biocontainers/blast:2.12.0--pl5262h3289130_0`

## Inputs
- `tuple val(meta), path(fasta)`: Metadata and FASTA file to be queried.
- `path db`: Database to search against.

## Outputs
- `tuple val(meta), path('*.blastn.txt')` (emit: txt): BLASTN tabular results.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses BLASTN directly; no custom bin script.

## Script Section Explanation
- Writes header to output file, runs BLASTN remotely, and appends results.
- Captures BLASTN version information in `versions.yml`.

---

# Example Command
```
blastn -db <db> -remote -query <fasta> <args> >> <output.txt>
```
