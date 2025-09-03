# BEDTOOLS_DEPTHCOVERAGE

## Overview
The `BEDTOOLS_DEPTHCOVERAGE` module calculates coverage statistics for genomic features using BED and BAM files, leveraging bedtools. It is used to assess how well sequencing reads cover specific genomic regions.

## Container
- Docker/Singularity: `biocontainers/bedtools:2.31.1--hf5e1c6e_0`
- Conda: uses `${moduleDir}/environment.yml` (should specify bedtools)

## Big Picture
This module splits a BED file by chromosome/contig, then computes coverage for each region using the provided BAM file. The results are aggregated into a single coverage report for the sample.

## Input
- `tuple val(meta), path(bed), path(bam)`

## Output
- `tuple val(meta), path("*.features.coverage")` (coverage report)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Splits the input BED file by chromosome/contig using `awk`.
- For each split BED file, runs `bedtools coverage` to compute coverage statistics against the BAM file.
- Aggregates all results into a single output file named `${meta.id}.features.coverage`.
- Writes out a `versions.yml` file with the bedtools version used.
