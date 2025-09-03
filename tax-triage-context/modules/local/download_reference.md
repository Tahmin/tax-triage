# REFERENCE

## Overview
The `REFERENCE` module generates a list of reference sequences for a given taxonomic ID (taxid) using a provided assembly file. It is used to map taxonomic identifiers to reference genome sequences for downstream analysis.

## Container
- Docker/Singularity: `biocontainers/gawk:4.2.0` (or `gawk:4.2.0` for Singularity)
- Conda: `conda-forge::python=3.8.3` (if enabled)

## Big Picture
This module takes a taxonomic ID and an assembly file, and produces a file listing the reference sequences associated with that taxid. This is essential for workflows that require mapping between taxonomy and reference genomes.

## Input
- `tuple val(meta), val(taxid)` (sample metadata and taxonomic ID)
- `path(assembly)` (assembly file)

## Output
- `path("*.ftmp")` (reference list file for the taxid)
- `path "versions.yml"` (software versions)

## Uses bin script?
- Yes: `taxid_to_reflist.sh` (located in `bin/`)

## Script Section
- Runs `taxid_to_reflist.sh` with the taxid and assembly file, producing a `.ftmp` file listing the reference sequences for the taxid.
- Writes out a `versions.yml` file with the awk version used.
