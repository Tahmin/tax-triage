# MINIMAP2_ALIGN Module

## Big Picture
The `MINIMAP2_ALIGN` module performs sequence alignment using minimap2, producing PAF and/or BAM files for downstream analysis. It supports both single-end and paired-end reads and can output in different formats based on parameters.

## Process Name
`MINIMAP2_ALIGN`

## Container/Conda Environment
- **Conda:** `bioconda::minimap2=2.21 bioconda::samtools=1.12` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/mulled-v2-66534bcbb7031a148b13e2ad42583020b9cd25c4:1679e915ddb9d6b4abda91880c4b48857d471bd8-0`
  - Docker: `biocontainers/mulled-v2-66534bcbb7031a148b13e2ad42583020b9cd25c4:1679e915ddb9d6b4abda91880c4b48857d471bd8-0`

## Inputs
- `tuple val(meta), path(reads)`: Metadata and reads file(s) to be aligned.
- `path reference`: Reference genome or sequence.
- `val bam_format`: Boolean flag for BAM output.
- `val cigar_paf_format`: Boolean flag for CIGAR in PAF output.
- `val cigar_bam`: Boolean flag for CIGAR in BAM output.

## Outputs
- `tuple val(meta), path("*.paf")` (emit: paf): PAF alignment file (optional).
- `tuple val(meta), path("*.bam")` (emit: bam): BAM alignment file (optional).
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- No custom bin script; uses minimap2 and samtools directly.

## Script Section Explanation
- Decompresses reads and runs minimap2 with provided arguments and reference.
- Outputs PAF or BAM files depending on parameters.
- Captures minimap2 version information in `versions.yml`.

---

# Example Command
```
gzip -dc <reads> | minimap2 <args> -t <cpus> <reference> <input_reads> <cigar_paf> <set_cigar_bam> <bam_output>
```
