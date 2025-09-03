# filter_reads.nf

## Overview

The `filter_reads.nf` subworkflow filters sequencing reads based on quality, length, or other criteria. This step ensures that only high-quality data is used in downstream analyses.

## Big Picture

Filtering improves the accuracy of alignment, assembly, and classification by removing low-quality or contaminant reads.

## Detailed Workflow

1. **Input**: Receives raw or pre-processed reads.
2. **Filtering**: Applies quality, length, or complexity filters (e.g., using fastp, Trimmomatic).
3. **Output**: Produces filtered reads for further processing.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/kraken2/kraken2/main
- ../../modules/local/moveFiles.nf

---

*See `filter_reads.nf` for details on filtering criteria and tools.*
