# FILTER_CLASS_READS

## Overview
The `FILTER_CLASS_READS` module filters sequencing reads based on classification results, producing a FASTQ file of reads that meet the specified criteria.

## Container
- Docker/Singularity: `biocontainers/biopython:1.75` (or `biopython:1.78` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes classified reads and filters them according to the provided classification and input files, outputting a filtered FASTQ file for downstream analysis.

## Input
- `tuple val(meta), path(bam), path(classified_reads), path(reads)`

## Output
- `path "versions.yml"` (software versions)
- `tuple val(meta), path("*.fastq")` (filtered reads)

## Uses bin script?
- Yes: `filter_reads.py` (located in `bin/`)

## Script Section
- Runs `filter_reads.py` with the classified reads and input reads, producing a filtered FASTQ file.
- Writes out a `versions.yml` file with the Python version used.
