# alignment.nf

## Overview

The `alignment.nf` subworkflow aligns metagenomic sequencing reads to a reference genome or database. This step is essential for identifying which organisms are present in a sample and for downstream analyses such as host read removal or variant calling.

## Big Picture

After initial quality control and filtering, reads are mapped to a reference. This mapping allows the pipeline to distinguish between host and microbial reads, and to quantify the abundance of different taxa.

## Detailed Workflow

1. **Input**: Receives quality-controlled reads and a reference genome/database.
2. **Alignment**: Uses an aligner (e.g., BWA, Bowtie2, or minimap2) to map reads to the reference.
3. **Post-processing**: May include sorting, indexing, and filtering of alignment files (e.g., with SAMtools).
4. **Output**: Produces alignment files (SAM/BAM) for downstream steps.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/bwa/index/main
- ../../modules/nf-core/bwa/mem/main
- ../../modules/nf-core/minimap2/align/main
- ../../modules/nf-core/minimap2/index/main
- ../../modules/nf-core/hisat2/align/main
- ../../modules/nf-core/samtools/depth/main
- ../../modules/nf-core/samtools/faidx/main
- ../../modules/nf-core/samtools/index/main
- ../../modules/nf-core/samtools/merge/main
- ../../modules/nf-core/samtools/coverage/main
- ../../modules/local/samtools_hist_coverage
- ../../modules/nf-core/bcftools/consensus/main
- ../../modules/nf-core/bcftools/mpileup/main
- ../../modules/nf-core/bcftools/index/main
- ../../modules/nf-core/bcftools/stats/main
- ../../modules/local/merge_fasta
- ../../modules/local/split_vcf
- ../../modules/nf-core/bowtie2/align/main
- ../../modules/nf-core/rseqc/bamstat/main
- ../../modules/local/bedtools_coverage
- ../../modules/local/bedtools_genomcov
- ../../modules/nf-core/bedtools/bamtobed/main
- ../../modules/nf-core/bedtools/maskfasta/main

---

*Check the `alignment.nf` code for exact module and tool usage.*
