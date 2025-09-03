# reference_assembly.nf

## Overview

The `reference_assembly.nf` subworkflow assembles reference genomes from sequencing data. This is useful for generating custom references for downstream analyses.

## Big Picture

Reference assembly is performed when suitable reference genomes are not available, or when constructing strain-specific references.

## Detailed Workflow

1. **Input**: Receives reads for reference assembly.
2. **Assembly**: Uses an assembler to build reference contigs.
3. **Output**: Produces assembled reference sequences.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/bcftools/consensus/main
- ../../modules/nf-core/bcftools/mpileup/main

---

*Refer to `reference_assembly.nf` for details on the assembly process.*
