# UNMAPPED_MINIMAP2 Module

## Big Picture
The `UNMAPPED_MINIMAP2` module aligns reads to a reference using minimap2 and samtools, producing sorted BAM files for downstream analysis. It automatically selects mapping presets based on platform.

## Process Name
`UNMAPPED_MINIMAP2`

## Container/Conda Environment
- **Conda:** `bioconda::minimap2=2.21 bioconda::samtools=1.12` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/mulled-v2-66534bcbb7031a148b13e2ad42583020b9cd25c4:1679e915ddb9d6b4abda91880c4b48857d471bd8-0`
  - Docker: `biocontainers/mulled-v2-66534bcbb7031a148b13e2ad42583020b9cd25c4:1679e915ddb9d6b4abda91880c4b48857d471bd8-0`

## Inputs
- `tuple val(meta), path(reads), path(reference)`: Metadata, reads file(s), and reference genome.

## Outputs
- `tuple val(meta), path("*.bam")` (emit: bam, optional): Sorted BAM file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses minimap2 and samtools directly; no custom bin script.

## Script Section Explanation
- Selects mapping preset based on platform, runs minimap2 and samtools to produce sorted BAM file.
- Captures minimap2 version information in `versions.yml`.

---

# Example Command
```
minimap2 <args> <preset> -a -t <cpus> -I <I_value> <reference> <input_reads> | samtools sort ... | samtools view ... -o <output.bam>
```
