# Minimap2 Modules

This directory contains modules for working with Minimap2, a fast sequence alignment program for mapping DNA or mRNA sequences against a large reference database.

---

## align
- **Purpose:** Aligns sequencing reads to a reference genome using Minimap2.
- **Main Files:**
  - `main.nf`: Nextflow process for alignment.
  - `meta.yml`: Module metadata.
- **Inputs:** Sequencing reads (FASTQ files), reference genome.
- **Outputs:** Aligned reads (SAM/BAM/PAF files).

## index
- **Purpose:** Builds Minimap2 index files from a reference genome.
- **Main Files:**
  - `main.nf`: Nextflow process for index building.
  - `meta.yml`: Module metadata.
- **Inputs:** Reference genome (FASTA file).
- **Outputs:** Minimap2 index files.

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call Minimap2 commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Minimap2 command for its function (e.g., `minimap2`, `minimap2 -d`).

---

# Example Commands
```
minimap2 -ax sr <ref.fa> <reads.fq> > <output.sam>
minimap2 -d <index.mmi> <ref.fa>
```

See the Minimap2 documentation for more details on usage and parameters.
