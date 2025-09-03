# FEATURES_TO_BED

## Overview
The `FEATURES_TO_BED` module converts a tab-delimited features file (e.g., from GenBank or GFF) into BED format, extracting coding sequence (CDS) regions for downstream analysis.

## Container
- Docker/Singularity: `biocontainers/gawk:4.2.0`
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module parses a features file, extracts CDS entries, and outputs them in BED format for use in coverage and annotation analyses.

## Input
- `tuple val(meta), path(features)` (features file, tab-delimited)

## Output
- `tuple val(meta), path("*.features.bed")` (BED file of CDS regions)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Uses `awk` to extract lines where the first column is "CDS" and the start is less than the end.
- Outputs chromosome, start, end, and gene name to a BED file named `${meta.id}.features.bed`.
- Writes out a `versions.yml` file with the Python version used.
