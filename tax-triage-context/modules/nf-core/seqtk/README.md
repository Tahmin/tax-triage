# Seqtk Modules

This directory contains modules for working with Seqtk, a fast and lightweight tool for processing sequences in the FASTA/FASTQ format.

---

## sample
- **Purpose:** Randomly samples reads from FASTA/FASTQ files.
- **Main Files:**
  - `main.nf`: Nextflow process for sampling.
  - `meta.yml`: Module metadata.
- **Inputs:** FASTA/FASTQ files.
- **Outputs:** Sampled FASTA/FASTQ files.

## seq
- **Purpose:** Performs sequence manipulation (e.g., reverse complement, subsequence extraction).
- **Main Files:**
  - `main.nf`: Nextflow process for sequence manipulation.
  - `meta.yml`: Module metadata.
- **Inputs:** FASTA/FASTQ files.
- **Outputs:** Manipulated FASTA/FASTQ files.

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call Seqtk commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Seqtk command for its function (e.g., `seqtk sample`, `seqtk seq`).

---

# Example Commands
```
seqtk sample <input.fq> <num_reads> > <output.fq>
seqtk seq -r <input.fq> > <output.fq>
```

See the Seqtk documentation for more details on usage and parameters.
