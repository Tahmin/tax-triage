# KREPORT_TO_KRONATXT

## Overview
The `KREPORT_TO_KRONATXT` module converts a Kraken2 report into a Krona-compatible text file for interactive visualization.

## Container
- Docker/Singularity: `biocontainers/biopython:1.75` (or `biopython:1.78` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes a Kraken2 report and generates a text file that can be used as input for Krona plots, enabling interactive exploration of taxonomic profiles.

## Input
- `tuple val(meta), path(kraken_report)`

## Output
- `tuple val(meta), path("*krakenreport.krona.txt")` (Krona-compatible text file)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `make_kt_files.py` (located in `bin/`)

## Script Section
- Runs `make_kt_files.py` with the Kraken2 report as input, producing a Krona-compatible text file.
- Writes out a `versions.yml` file with the Python version used.
