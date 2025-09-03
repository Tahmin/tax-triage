# DOWNLOAD_PATHOGENS

## Overview
The `DOWNLOAD_PATHOGENS` module downloads a reference FASTA file containing pathogen sequences for use in downstream analysis.

## Container
- Docker/Singularity: `biocontainers/gnu-wget:1.18--h36e9172_9` (or `gnu-wget:1.18--h7132678_6` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the retrieval of a curated set of pathogen reference sequences, which are used for mapping, classification, or filtering in the pipeline.

## Input
- No explicit input; the module downloads a fixed URL.

## Output
- `path("pathogens.fasta")` (downloaded and decompressed pathogen reference FASTA)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Uses `wget` to download a gzipped FASTA file of pathogen sequences from a public repository.
- Decompresses the file with `gzip -d` to produce `pathogens.fasta`.
