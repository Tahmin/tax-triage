# MOVE_NANOPLOT Module

## Big Picture
The `MOVE_NANOPLOT` module renames and moves NanoPlot HTML and stats files to standardized output filenames for downstream reporting and MultiQC compatibility.

## Process Name
`MOVE_NANOPLOT`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(html), path(stats)`: Metadata, NanoPlot HTML, and stats files.

## Outputs
- `tuple val(meta), path("*_mqc.html")` (emit: html): Renamed NanoPlot HTML file.
- `tuple val(meta), path("*NanoStats.txt")` (emit: stats): Renamed NanoPlot stats file.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses shell commands to rename/move files; no custom bin script.

## Script Section Explanation
- Iterates over HTML and stats files, renaming them to include the sample ID and standard suffixes.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
for i in <html_files>; do mv $i <sample_id>_$i_mqc.html; done
for i in <stats_files>; do mv $i <sample_id>_$i; done
```
