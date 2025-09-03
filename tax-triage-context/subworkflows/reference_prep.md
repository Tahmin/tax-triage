# reference_prep.nf

## Overview

The `reference_prep.nf` subworkflow prepares reference genomes or databases for use in alignment or classification. This may include indexing or formatting steps.

## Big Picture

Properly prepared references are essential for efficient and accurate alignment and classification.

## Detailed Workflow

1. **Input**: Receives raw reference sequences.
2. **Preparation**: Indexes or formats references for downstream tools.
3. **Output**: Provides ready-to-use reference files.

## Included Modules

**Exact module paths included:**

- ../../modules/local/make_file
- ../../modules/local/download_assembly
- ../../modules/local/map_assembly_to_fasta
- ../../modules/local/map_taxid_assembly
- ../../modules/local/download_features
- ../../modules/local/convert_features_to_bed
- ../../modules/local/combine_mapfiles
- ../../modules/nf-core/bowtie2/build/main
- ../../modules/nf-core/hisat2/build/main

---

*See `reference_prep.nf` for the specific preparation steps.*
