# Bowtie2 Modules

This directory contains modules for working with Bowtie2, a fast and memory-efficient tool for aligning sequencing reads to long reference sequences.

---

## align
- **Purpose:** Aligns sequencing reads to a reference genome using Bowtie2.
- **Main Files:**
  - `main.nf`: Nextflow process for alignment.
  - `meta.yml`: Module metadata.
- **Inputs:** Sequencing reads (FASTQ files), reference genome.
- **Outputs:** Aligned reads (SAM/BAM files).

## build
- **Purpose:** Builds Bowtie2 index files from a reference genome.
- **Main Files:**
  - `main.nf`: Nextflow process for index building.
  - `meta.yml`: Module metadata.
- **Inputs:** Reference genome (FASTA file).
- **Outputs:** Bowtie2 index files.

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call Bowtie2 commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Bowtie2 command for its function (e.g., `bowtie2`, `bowtie2-build`).

---

# Example Commands
```
bowtie2 -x <index> -1 <reads_1.fq> -2 <reads_2.fq> -S <output.sam>
bowtie2-build <reference.fa> <index_prefix>
```

See the Bowtie2 documentation for more details on usage and parameters.
