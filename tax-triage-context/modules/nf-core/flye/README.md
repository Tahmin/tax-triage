# Flye Module

## Big Picture
The `flye` module runs Flye, a de novo assembler for long noisy reads, such as those from PacBio or Oxford Nanopore.

## Main Files
- `main.nf`: Nextflow process definition for Flye.
- `meta.yml`: Module metadata.

## Inputs
- Long-read sequencing data (FASTQ files).

## Outputs
- Assembled contigs (FASTA files) and assembly reports.

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Flye container/environment.

## Use of bin Scripts
- Calls Flye directly; no custom bin script in this module.

## Script Section Explanation
- Runs Flye with user-specified parameters for genome assembly.

---

# Example Command
```
flye --nano-raw <reads.fastq> --out-dir <output_dir> --genome-size <size> [options]
```

See the Flye documentation for more details on usage and parameters.
