# DOWNLOAD_ASSEMBLY

## Overview
The `DOWNLOAD_ASSEMBLY` module downloads reference genome assemblies based on a list of hits or IDs, producing FASTA files and mapping tables for downstream analysis.

## Container
- Docker/Singularity: `biocontainers/biopython:1.75` (or `pegi3s/biopython:latest` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the retrieval of reference genome sequences and their associated metadata, ensuring that all required references are available for mapping and annotation.

## Input
- `tuple val(meta), path(hits_containing_file)` (file with list of hits/IDs)
- `path assembly` (assembly file)

## Output
- `tuple val(meta), path("*.dwnld.references.fasta")` (downloaded reference FASTA)
- `tuple val(meta), path("*.dwnld.gcfids.txt")` (list of downloaded GCF IDs)
- `tuple val(meta), path("*.dwnld.gcfmapping.tsv")` (mapping table)
- `tuple val(meta), path("missing.txt")` (missing references, if any)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `download_fastas.py` (located in `bin/`)

## Script Section
- Runs `download_fastas.py` with the input list and assembly file, producing a reference FASTA, mapping table, and missing list.
- Extracts unique GCF IDs from the mapping table.
- Writes out a `versions.yml` file with the Python version used.
