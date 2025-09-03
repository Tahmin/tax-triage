# host_removal.nf

## Overview

The `host_removal.nf` subworkflow removes host-derived reads from metagenomic datasets. This step is essential for focusing analysis on microbial content and reducing host contamination.

## Big Picture

Host removal is performed after alignment, using the host genome as a reference. Reads mapping to the host are discarded, and the remaining reads are used for microbial analysis.

## Detailed Workflow

1. **Input**: Receives reads and a host reference genome.
2. **Alignment**: Maps reads to the host genome.
3. **Filtering**: Removes reads that align to the host.
4. **Output**: Produces non-host reads for downstream analysis.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/minimap2/align/main
- ../../modules/nf-core/minimap2/index/main
- ../../modules/nf-core/kraken2/kraken2/main
- ../../modules/nf-core/samtools/view/main
- ../../modules/local/remove_unaligned
- ../../modules/nf-core/samtools/index/main
- ../../modules/nf-core/samtools/stats/main
- ../../modules/local/check_reads_exist
- ../../modules/local/download_db

---

*Check `host_removal.nf` for the specific modules and tools used.*
