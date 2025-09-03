# DOWNLOAD_TAXTAB

## Overview
The `DOWNLOAD_TAXTAB` module downloads a tab-delimited taxonomy table for use in downstream classification and annotation.

## Container
- Docker/Singularity: `biocontainers/gnu-wget:1.18--h36e9172_9` (or `gnu-wget:1.18--h7132678_6` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the retrieval of a pre-formatted taxonomy table, which is required for certain taxonomic classification and mapping steps.

## Input
- No explicit input; the module downloads a fixed URL.

## Output
- `path("taxonomy.tab")` (downloaded taxonomy table)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Uses `wget` to download a gzipped taxonomy table from a public repository.
- Decompresses the file with `gzip -d` to produce `taxonomy.tab`.
