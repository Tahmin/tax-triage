# SPLIT_READS Module

## Big Picture
The `SPLIT_READS` module splits reads from FASTQ files based on mapping information, producing separate FASTQ files for downstream analysis.

## Process Name
`SPLIT_READS`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), path(fastq), path(fasta), path(reads)`: Metadata, FASTQ, FASTA, and mapping file.

## Outputs
- `tuple val(meta), path("**/*fastq")` (emit: split_reads): Split FASTQ files.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `split_reads.py` from the pipeline's `bin/` directory to split reads.

## Script Section Explanation
- Runs `split_reads.py` with mapping and FASTQ files, outputs split reads.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
split_reads.py -m <reads> -o <output_dir> -q <fastq>
```
