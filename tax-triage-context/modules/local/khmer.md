# KHMER_NORMALIZEBYMEDIAN

## Overview
The `KHMER_NORMALIZEBYMEDIAN` module normalizes sequencing read coverage using the khmer toolkit, producing normalized FASTQ files for downstream assembly or analysis.

## Container
- Docker/Singularity: `biocontainers/khmer:3.0.0a3--py37haa7609a_2` (or `khmer:3.0.0a3--py37haa7609a_2` for Singularity)
- Conda: uses `${moduleDir}/environment.yml` (should specify khmer)

## Big Picture
This module uses khmer's `normalize-by-median.py` to reduce coverage bias in sequencing data, improving assembly and downstream analyses.

## Input
- `tuple val(meta), path(files)` (input FASTQ files)

## Output
- `tuple val(meta), path("${meta.id}.normalized_*.fastq.gz")` (normalized FASTQ files)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Calculates available memory and runs `normalize-by-median.py` with appropriate options for single-end or paired-end data.
- For paired-end data, splits the output into R1 and R2 files.
- Writes out a `versions.yml` file with the khmer version used.
