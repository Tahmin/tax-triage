# NCBIGENOMEDOWNLOAD_FEATURES

## Overview
The `NCBIGENOMEDOWNLOAD_FEATURES` module downloads feature tables for a set of genome assemblies using the `ncbi-genome-download` tool.

## Container
- Docker/Singularity: `biocontainers/ncbi-genome-download:0.3.3--pyh7cba7a3_0` (or `ncbi-genome-download:0.3.3--pyh7cba7a3_0` for Singularity)
- Conda: uses `${moduleDir}/environment.yml` (should specify ncbi-genome-download)

## Big Picture
This module automates the retrieval of feature tables for genome assemblies, supporting downstream annotation and comparative genomics.

## Input
- `tuple val(meta), path(gcf_file)` (GCF accession file)

## Output
- `tuple val(meta), path("*.features.txt")` (feature table)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Runs `ncbi-genome-download` to download feature tables for the specified assemblies.
- Decompresses any gzipped feature tables.
- Writes out a `versions.yml` file with the tool version used.
