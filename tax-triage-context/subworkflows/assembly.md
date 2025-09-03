# assembly.nf

## Overview

The `assembly.nf` subworkflow performs de novo assembly of metagenomic reads. This step reconstructs longer contiguous sequences (contigs) from short sequencing reads, enabling the discovery of novel genomes and genes within the sample.

## Big Picture

Assembly is crucial for characterizing the genetic content of complex microbial communities, especially when reference genomes are incomplete or unavailable. It enables downstream analyses such as gene prediction, binning, and functional annotation.

## Detailed Workflow

1. **Input**: Receives quality-controlled, filtered reads.
2. **Assembly**: Uses an assembler (e.g., MEGAHIT, metaSPAdes) to build contigs from reads.
3. **Post-processing**: May include filtering contigs by length or coverage.
4. **Output**: Produces assembled contigs for further analysis.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/megahit/main
- ../../modules/nf-core/diamond/makedb/main
- ../../modules/nf-core/diamond/blastx/main
- ../../modules/nf-core/bedtools/coverage/main
- ../../modules/local/features_map
- ../../modules/local/map_prot_assembly
- ../../modules/nf-core/flye/main

---

*See `assembly.nf` for specific modules and tools used.*
