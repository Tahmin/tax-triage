# CONVERT_METRICS

## Overview
The `CONVERT_METRICS` module merges and reformats confidence metric tables for a sample, producing a unified summary for downstream analysis in the tax-triage pipeline.

## Container
- Docker/Singularity: `biocontainers/biopython:1.75` (or `biopython:1.78` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes one or more metrics TSV files and merges them into a single, reformatted summary table for each sample.

## Input
- `tuple val(meta), path(tsv)` (input metrics TSV file)

## Output
- `path("*metrics.merged.tsv")` (merged metrics summary table)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `mergeConfidence.py` (located in `bin/`)

## Script Section
- Runs `mergeConfidence.py` with the input TSV file and sample ID, producing a merged metrics summary table.
- Writes out a `versions.yml` file with the Python version used.
