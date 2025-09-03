# REMOVE_HOSTREADS Module

## Big Picture
The `REMOVE_HOSTREADS` module removes host-aligned reads from sequencing data using samtools, producing host-removed FASTQ files for downstream analysis.

## Process Name
`REMOVE_HOSTREADS`

## Container/Conda Environment
- **Conda:** `bioconda::samtools=1.17`
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/samtools:1.17--h00cdaf9_0`
  - Docker: `biocontainers/samtools:1.17--h00cdaf9_0`

## Inputs
- `tuple val(meta), path(input)`: Metadata and input BAM file(s).

## Outputs
- `tuple val(meta), path("*.hostremoved.{fastq,fq}.gz")` (emit: reads): Host-removed FASTQ files (optional).
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses samtools directly; no custom bin script.

## Script Section Explanation
- Runs samtools to filter and convert BAM to host-removed FASTQ files, with options for single/paired-end and platform-specific output.
- Captures samtools version information in `versions.yml`.

---

# Example Command
```
samtools view -b <flag> <input> | samtools fastq <cmd> - <args> -n
```
