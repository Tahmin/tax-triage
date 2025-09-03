# FEATURES_MAP

## Overview
The `FEATURES_MAP` module maps coverage and mapping information to genomic features, producing detailed tables for each contig and organism.

## Container
- Docker/Singularity: `biocontainers/pysam:0.21.0--py39hcada746_1` (or `pysam:0.21.0--py39hcada746_1` for Singularity)
- Conda: `conda-forge::python=3.8.3 pysam` (if enabled)

## Big Picture
This module takes coverage and mapping files and produces feature-level summary tables for each contig and organism, supporting downstream functional and comparative analyses.

## Input
- `tuple val(meta), path(covfile), path(mapping)` (coverage and mapping files)

## Output
- `tuple val(meta), path("*.features.individual.contig.tsv")` (contig-level feature table)
- `tuple val(meta), path("*.features.organism.tsv")` (organism-level feature table)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `features_map.py` (located in `bin/`)

## Script Section
- Runs `features_map.py` with the coverage and mapping files, producing both contig-level and organism-level feature tables.
- Writes out a `versions.yml` file with the Python version used.
