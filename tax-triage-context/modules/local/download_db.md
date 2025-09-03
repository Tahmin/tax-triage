# DOWNLOAD_DB

## Overview
The `DOWNLOAD_DB` module downloads and verifies a Kraken2-compatible database from a specified URL, ensuring all required files are present for downstream classification.

## Container
- Docker/Singularity: `biocontainers/gnu-wget:1.18--h36e9172_9` (or `gnu-wget:1.18--h7132678_6` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module automates the download and verification of a Kraken2 database, which is essential for taxonomic classification steps in the pipeline.

## Input
- `val(db)` (database name or identifier)
- `val(url)` (URL to download the database)
- `val(checksum)` (expected checksum for verification)

## Output
- `path("**/*hash.k2d")` (hash file)
- `path("**/*opts.k2d")` (options file)
- `path("**/*taxo.k2d")` (taxonomy file)

## Uses bin script?
- Yes: `download_db.sh` (located in `bin/`)

## Script Section
- Runs `download_db.sh` with the database name, URL, and checksum as arguments.
- The script downloads the database, verifies its integrity, and extracts the required files for Kraken2.
