# FILTERKRAKEN

## Overview
The `FILTERKRAKEN` module filters Kraken2 classification reports, producing filtered summary tables for downstream analysis and reporting.

## Container
- Docker/Singularity: `biocontainers/python:3.8.3` (or `python:3.9--1` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes a Kraken2 report and filters it to produce summary tables at various taxonomic levels, supporting downstream visualization and reporting.

## Input
- `path krakenreport` (Kraken2 report file)

## Output
- `path("*_filtered_mqc.tsv")` (filtered summary table)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `filter_tsv.py` (located in `bin/`)

## Script Section
- Runs `filter_tsv.py` with the Kraken2 report as input, producing filtered summary tables for MultiQC and other reporting tools.
- Writes out a `versions.yml` file with the Python version used.
