# COMBINE_MAPFILES

## Overview
The `COMBINE_MAPFILES` module merges and deduplicates mapping files and ID lists, producing combined outputs for downstream reference mapping and annotation steps.

## Container
- Docker/Singularity: `biocontainers/gawk:4.2.0`
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes lists of mapping files and ID files, sorts and deduplicates them, and outputs unified files for use in later steps of the pipeline.

## Input
- `tuple val(meta), path(gcfmaps), path(gcfids)`

## Output
- `tuple val(meta), path("*.combined.gcfmap.tsv"), path("*.combined.gcfids.txt")` (combined mapping and ID files)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Concatenates, sorts, and deduplicates the input ID files into a single `.combined.gcfids.txt` file.
- Concatenates, sorts, and deduplicates the input mapping files into a single `.combined.gcfmap.tsv` file.
- Writes out a `versions.yml` file (note: attempts to record wget version, but wget is not used in the script).
