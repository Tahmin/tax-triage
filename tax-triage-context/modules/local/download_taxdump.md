# DOWNLOAD_TAXDUMP

## Overview
The `DOWNLOAD_TAXDUMP` module downloads and extracts the NCBI taxonomy dump, providing taxonomy files for downstream classification and annotation.

## Container
- Docker/Singularity: `biocontainers/gnu-wget:1.18--h36e9172_9` (or `gnu-wget:1.18--h7132678_6` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the retrieval and extraction of the NCBI taxonomy database, which is required for taxonomic classification and mapping.

## Input
- No explicit input; the module downloads a fixed URL.

## Output
- `path("names.dmp")` (taxonomy names file)
- `path("nodes.dmp")` (taxonomy nodes file)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Uses `wget` to download the NCBI taxonomy dump as a tar.gz archive.
- Extracts the archive with `tar -xvzf` and removes the tar.gz file.
