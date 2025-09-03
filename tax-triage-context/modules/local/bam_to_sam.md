# BAM_TO_SAM

## Overview
The `BAM_TO_SAM` module converts BAM alignment files to SAM format and generates a pileup file for downstream analysis in the tax-triage pipeline.

## Container
- Docker/Singularity: `biocontainers/samtools:1.15.1--h1170115_0`
- Conda: `bioconda::samtools=1.15.1` (if enabled)

## Big Picture
This module takes a BAM file (binary alignment) and produces a SAM file (text alignment) and a pileup file, which are useful for variant calling, visualization, and other downstream analyses.

## Input
- `tuple val(meta), path(bamfiles)`

## Output
- `path "versions.yml"` (software versions)
- `tuple val(meta), path("*.sam")` (SAM file)
- `path("*.mpileup")` (pileup file)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Runs `samtools view` to convert BAM to SAM format (optionally filtering for paired-end reads).
- Sorts the SAM output.
- Runs `samtools mpileup` to generate a pileup file from the SAM file.
- Writes out a `versions.yml` file with the Python version used.
