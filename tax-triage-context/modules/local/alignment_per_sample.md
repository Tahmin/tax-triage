# ALIGNMENT_PER_SAMPLE

## Overview
The `ALIGNMENT_PER_SAMPLE` module processes alignment results for a single sample, integrating multiple sources of evidence (alignment, coverage, taxonomy, etc.) to generate a comprehensive report for downstream analysis in the tax-triage pipeline.

## Container
- Docker/Singularity: `jhuaplbio/taxtriage_confidence:2.1`
- Conda: `bioconda::pysam` (if enabled)

## Big Picture
This module takes alignment and annotation results for a sample and runs a scoring and matching script to produce a summary of detected organisms, their confidence scores, and supporting evidence. It is a key step in generating the final confidence report for each sample.

## Input
- `tuple val(meta), path(bamfiles), path(bai), path(mapping), path(bedgraph), path(covfile), path(k2_report), path(ch_diamond_analysis), path(fastas), path(pathogens_list)`
- `file assembly`

## Output
- `path "versions.yml"` (software versions)
- `tuple val(meta), path("*.txt")` (main output report)

## Uses bin script?
- Yes: `match_paths.py` (located in `bin/`)

## Script Section
The script dynamically constructs a command to run `match_paths.py` with all relevant input files and parameters, including:
- Alignment files (BAM, BAI)
- Mapping and coverage files
- Taxonomic reports (Kraken2, Diamond)
- Pathogen lists and reference FASTAs
- Various scoring and weighting parameters

The script then runs `match_paths.py` to generate a summary report for the sample, and writes out a `versions.yml` file with the Python version used.
