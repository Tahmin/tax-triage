# classifier.nf

## Overview

The `classifier.nf` subworkflow assigns taxonomic labels to metagenomic reads or contigs. This step determines the composition of microbial communities by identifying which organisms are present in the sample.

## Big Picture

Classification is a core part of metagenomics, enabling the quantification and comparison of taxa across samples. It is typically performed after host removal and/or assembly.

## Detailed Workflow

1. **Input**: Receives reads or contigs (assembled or unassembled).
2. **Classification**: Uses a taxonomic classifier (e.g., Kraken2, Centrifuge, Kaiju) to assign taxonomy.
3. **Output**: Produces classification reports and abundance tables.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/metaphlan/metaphlan/main
- ../../modules/nf-core/kraken2/kraken2/main
- ../../modules/local/top_hits
- ../../modules/local/remove_taxids.nf
- ../../modules/local/krakenreport
- ../../modules/nf-core/taxpasta/standardise/main
- ../../modules/nf-core/taxpasta/merge/main
- ../../modules/local/merged_krakenreport
- ../../modules/local/filter_krakenreport
- ../../modules/local/generate_krona_txtfile
- ../../modules/local/kreport_to_taxonomy
- ../../modules/local/krona.nf
- ../../modules/local/extract_top_seqs.nf
- ../../modules/nf-core/krona/ktimporttext/main
- ../../modules/nf-core/krakentools/combinekreports/main
- ../../modules/local/merged_subspecies

---

*Refer to `classifier.nf` for the exact modules and classifiers used.*
