# BEDTools Modules

This directory contains several modules for working with BEDTools, a suite for genome arithmetic and manipulation of genomic intervals. Each submodule provides a specific function for processing genomic data.

---

## bamtobed
- **Purpose:** Converts BAM files to BED format for downstream interval analysis.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM to BED conversion.
  - `environment.yml`: Conda environment for BEDTools.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** BAM files.
- **Outputs:** BED files.

## coverage
- **Purpose:** Computes coverage of features in BED files over reference intervals.
- **Main Files:**
  - `main.nf`: Nextflow process for coverage calculation.
  - `environment.yml`: Conda environment for BEDTools.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** BED files, reference intervals.
- **Outputs:** Coverage statistics.

## maskfasta
- **Purpose:** Masks regions in FASTA files based on BED intervals.
- **Main Files:**
  - `main.nf`: Nextflow process for masking FASTA files.
  - `environment.yml`: Conda environment for BEDTools.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** FASTA files, BED intervals.
- **Outputs:** Masked FASTA files.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml`).

## Use of bin Scripts
- Modules call BEDTools commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate BEDTools command for its function (e.g., `bedtools bamtobed`, `bedtools coverage`, `bedtools maskfasta`).

---

# Example Commands
```
bedtools bamtobed -i <input.bam> > <output.bed>
bedtools coverage -a <features.bed> -b <reference.bed> > <output.txt>
bedtools maskfasta -fi <input.fa> -bed <regions.bed> -fo <output.fa>
```

See the BEDTools documentation for more details on usage and parameters.
