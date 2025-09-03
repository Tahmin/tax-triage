# PULL_TAXID Module

## Big Picture
The `PULL_TAXID` module downloads reference genome FASTA files based on assembly hits, decompresses them, and prepares them for downstream analysis.

## Process Name
`PULL_TAXID`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), val(assembly_hits)`: Metadata and assembly hits.
- `val row`: Row value (not used in script).

## Outputs
- `tuple val(meta), path("*.fasta")` (emit: genome): Downloaded and decompressed genome FASTA file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `refseq_download_single.sh` from the pipeline's `bin/` directory to download reference genomes.

## Script Section Explanation
- Creates output directory, runs `refseq_download_single.sh` to download genomes, and decompresses them.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
refseq_download_single.sh -i <assembly_hits> -o <output_dir>
gzip -d <output_dir>/*.gz
```
