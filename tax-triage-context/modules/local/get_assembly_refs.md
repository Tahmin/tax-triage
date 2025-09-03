# GET_ASSEMBLIES

## Overview
The `GET_ASSEMBLIES` module downloads the NCBI RefSeq assembly summary file, which lists all available reference genome assemblies.

## Container
- Docker/Singularity: `biocontainers/gnu-wget:1.18--h36e9172_9` (or `gnu-wget:1.18--h7132678_6` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module ensures the latest NCBI RefSeq assembly summary file is available for reference mapping and annotation steps in the pipeline.

## Input
- No explicit input; the module downloads a fixed URL if the file does not already exist.

## Output
- `path("assembly_summary_refseq.txt")` (NCBI RefSeq assembly summary)
- `path "versions.yml"` (software versions)

## Uses bin script?
- No external script from `bin/` is used; all commands are run directly in the script section.

## Script Section
- Checks if the assembly summary file exists; if not, downloads it from NCBI using `wget`.
- Writes out a `versions.yml` file with the wget version used.
