# CHECK_GZIPPED_READS

## Overview
The `CHECK_GZIPPED_READS` module checks whether gzipped FASTQ files contain at least a specified minimum number of reads. It is used for quality control to ensure sufficient data is present before downstream analysis.

## Container
- Docker/Singularity: `biocontainers/samtools:1.17--h00cdaf9_0`
- Conda: `bioconda::samtools=1.17`

## Big Picture
This module takes one or more gzipped FASTQ files and verifies that each contains at least the required number of reads. It outputs a file indicating whether the check passed or failed.

## Input
- `tuple val(meta), path(fastq_files)`
- `val(minimum_reads_check)` (minimum number of reads required)

## Output
- `tuple val(meta), path("{emptyfile,minimum_reads_check}.txt")` (result file, either `minimum_reads_check.txt` if failed, or `emptyfile.txt` if passed)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- For each input FASTQ file, decompresses with `gzip -dc` and counts lines with `wc -l`.
- If any file contains fewer than the required number of reads, writes a message to `minimum_reads_check.txt`.
- If all files pass, creates an empty file `emptyfile.txt`.
