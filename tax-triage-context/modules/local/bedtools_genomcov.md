# BEDTOOLS_GENOMECOVERAGE

## Overview
The `BEDTOOLS_GENOMECOVERAGE` module computes genome-wide coverage statistics from a BAM file and outputs the results in bedGraph format. This is useful for visualizing and quantifying read coverage across the genome.

## Container
- Docker/Singularity: `biocontainers/bedtools:2.31.1--hf5e1c6e_0`
- Conda: uses `${moduleDir}/environment.yml` (should specify bedtools)

## Big Picture
This module takes a BAM file containing mapped reads and produces a bedGraph file showing the depth of coverage at each position or region in the genome.

## Input
- `tuple val(meta), path(bam)`

## Output
- `tuple val(meta), path("*.bedgraph")` (bedGraph coverage file)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Runs `bedtools genomecov` with the `-ibam` and `-bg` options to generate a bedGraph file from the BAM input.
- Writes out a `versions.yml` file with the bedtools version used.
