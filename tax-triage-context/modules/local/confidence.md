# METRIC_ALIGNMENT

## Overview
The `METRIC_ALIGNMENT` module calculates alignment-based confidence metrics for a sample, producing a summary table of alignment statistics for downstream analysis in the tax-triage pipeline.

## Container
- Docker/Singularity: `biocontainers/pysam:0.21.0--py39hcada746_1`
- Conda: `conda-forge::python=3.8.3 pysam` (if enabled)

## Big Picture
This module takes alignment files and mapping information, runs a custom script to compute confidence metrics, and outputs a summary table for each sample.

## Input
- `tuple val(meta), path(bam), path(csi), path(depth), path(mapping)`

## Output
- `tuple val(meta), path("*.metrics.tsv")` (metrics summary table)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `sam_to_confidence.py` (located in `bin/`)

## Script Section
- Runs `sam_to_confidence.py` with the BAM file, depth file, and (optionally) mapping file as input.
- Produces a metrics summary table for the sample.
- Writes out a `versions.yml` file with the Python version used.
