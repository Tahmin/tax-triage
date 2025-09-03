# FEATURES_DOWNLOAD

## Overview
The `FEATURES_DOWNLOAD` module downloads and aggregates feature tables and protein sequences for a set of reference genomes, producing files for downstream annotation and analysis.

## Container
- Docker/Singularity: `biocontainers/biopython:1.75` (or `pegi3s/biopython:latest` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the retrieval and aggregation of feature tables and protein FASTA files for a set of reference genomes, enabling functional and comparative genomics analyses.

## Input
- `tuple val(meta), path(gcfs)` (list of GCF IDs or files)
- `path(assembly)` (assembly file)
- `val(get_aas)` (flag to indicate if protein sequences should be downloaded)

## Output
- `tuple val(meta), path("${meta.id}_features.txt")` (aggregated feature table)
- `tuple val(meta), path("${meta.id}_proteins.faa")` (aggregated protein FASTA, optional)
- `tuple val(meta), path("${meta.id}.map.txt")` (mapping file, optional)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `download_features.py` (located in `bin/`)

## Script Section
- Runs `download_features.py` with the input GCFs and assembly file, producing feature tables and protein FASTA files in an output directory.
- Concatenates all feature tables and protein FASTA files into single output files.
- Cleans up intermediate files, keeping only the final outputs.
- Writes out a `versions.yml` file with the Python version used.
