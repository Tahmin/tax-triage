# BWA Modules

This directory contains modules for working with BWA, a software package for mapping low-divergent sequences against a large reference genome.

---

## index
- **Purpose:** Builds BWA index files from a reference genome.
- **Main Files:**
  - `main.nf`: Nextflow process for index building.
  - `meta.yml`: Module metadata.
- **Inputs:** Reference genome (FASTA file).
- **Outputs:** BWA index files.

## mem
- **Purpose:** Aligns sequencing reads to a reference genome using the BWA-MEM algorithm.
- **Main Files:**
  - `main.nf`: Nextflow process for alignment.
  - `meta.yml`: Module metadata.
- **Inputs:** Sequencing reads (FASTQ files), reference genome.
- **Outputs:** Aligned reads (SAM/BAM files).

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call BWA commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate BWA command for its function (e.g., `bwa index`, `bwa mem`).

---

# Example Commands
```
bwa index <reference.fa>
bwa mem <reference.fa> <reads_1.fq> <reads_2.fq> > <output.sam>
```

See the BWA documentation for more details on usage and parameters.
