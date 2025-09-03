# SAMTOOLS_HIST_COVERAGE Module

## Big Picture
The `SAMTOOLS_HIST_COVERAGE` module generates coverage histograms from BAM files using samtools, providing coverage statistics for downstream analysis.

## Process Name
`SAMTOOLS_HIST_COVERAGE`

## Container/Conda Environment
- **Conda:** Uses environment from `${moduleDir}/environment.yml`
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/samtools:1.19.2--h50ea8bc_0`
  - Docker: `biocontainers/samtools:1.19.2--h50ea8bc_0`

## Inputs
- `tuple val(meta), path(bam), path(mapping)`: Metadata, BAM file, and mapping file.

## Outputs
- `tuple val(meta), path("*.histo.txt")` (emit: histogram): Coverage histogram file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `samtools_coverage.sh` from the pipeline's `bin/` directory to generate coverage histograms.

## Script Section Explanation
- Runs `samtools_coverage.sh` with BAM and mapping files, outputs coverage histogram.
- Captures samtools version information in `versions.yml`.

---

# Example Command
```
samtools_coverage.sh -b <bam> -o <output.txt> -c 4 <mapping> -a <args>
```
