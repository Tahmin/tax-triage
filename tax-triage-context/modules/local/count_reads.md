# COUNT_READS

## Overview
The `COUNT_READS` module counts the total number of reads in one or more FASTQ files (compressed or uncompressed) for a sample, outputting the result for downstream QC and reporting.

## Container
- Docker/Singularity: `biocontainers/gawk:4.2.0`
- Conda: `conda-forge::gawk` (if enabled)

## Big Picture
This module takes a set of FASTQ files and counts the number of sequencing reads, regardless of whether the files are gzipped or plain text. The result is used for quality control and to annotate sample metadata.

## Input
- `tuple val(meta), path(reads)` (one or more FASTQ files)

## Output
- `tuple val(meta), path("count.txt"), path(reads)` (read count and original reads)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Loops over each input file.
- If the file is gzipped, decompresses with `zcat` and counts reads using `awk` (one read per 4 lines).
- If the file is plain text, counts reads directly with `awk`.
- Sums the counts for all files and writes the total to `count.txt`.
