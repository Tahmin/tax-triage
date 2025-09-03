# HISAT2 Modules

This directory contains modules for working with HISAT2, a fast and sensitive alignment program for mapping next-generation sequencing reads to a reference genome.

---

## align
- **Purpose:** Aligns sequencing reads to a reference genome using HISAT2.
- **Main Files:**
  - `main.nf`: Nextflow process for alignment.
  - `environment.yml`: Conda environment for HISAT2.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** Sequencing reads (FASTQ files), reference genome.
- **Outputs:** Aligned reads (SAM/BAM files).

## build
- **Purpose:** Builds HISAT2 index files from a reference genome.
- **Main Files:**
  - `main.nf`: Nextflow process for index building.
  - `environment.yml`: Conda environment for HISAT2.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** Reference genome (FASTA file).
- **Outputs:** HISAT2 index files.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml`).

## Use of bin Scripts
- Modules call HISAT2 commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate HISAT2 command for its function (e.g., `hisat2`, `hisat2-build`).

---

# Example Commands
```
hisat2 -x <index> -1 <reads_1.fq> -2 <reads_2.fq> -S <output.sam>
hisat2-build <reference.fa> <index_prefix>
```

See the HISAT2 documentation for more details on usage and parameters.
