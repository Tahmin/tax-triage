# SAMTOOLS_SORT Module

## Big Picture
The `SAMTOOLS_SORT` module sorts BAM files using samtools, producing sorted BAM and index files for downstream analysis.

## Process Name
`SAMTOOLS_SORT`

## Container/Conda Environment
- **Conda:** Uses environment from `${moduleDir}/environment.yml`
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/samtools:1.18--h50ea8bc_1`
  - Docker: `biocontainers/samtools:1.18--h50ea8bc_1`

## Inputs
- `tuple val(meta), path(bam)`: Metadata and BAM file to be sorted.

## Outputs
- `tuple val(meta), path("*.bam")` (emit: bam): Sorted BAM file.
- `tuple val(meta), path("*.csi")` (emit: csi, optional): BAM index file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses samtools directly; no custom bin script.

## Script Section Explanation
- Runs samtools view and sort to produce sorted BAM and index files, with error handling for input/output name conflicts.
- Captures samtools version information in `versions.yml`.

---

# Example Command
```
samtools view <bam> -h -q <minmapq> | samtools sort <args> -@ <cpus> -o <output.bam> -T <prefix>
```
