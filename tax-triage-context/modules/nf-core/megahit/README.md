# MEGAHIT Module

## Big Picture
The `megahit` module runs MEGAHIT, a fast and memory-efficient assembler for large and complex metagenomics datasets.

## Main Files
- `main.nf`: Nextflow process definition for MEGAHIT.
- `environment.yml`: Conda environment for MEGAHIT.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Sequencing reads (FASTQ files).

## Outputs
- Assembled contigs (FASTA files) and assembly reports.

## Container/Conda Environment
- Defined in `environment.yml` (uses MEGAHIT tools).

## Use of bin Scripts
- Calls MEGAHIT directly; no custom bin script in this module.

## Script Section Explanation
- Runs MEGAHIT with user-specified parameters for metagenome assembly.

---

# Example Command
```
megahit -1 <reads_1.fq> -2 <reads_2.fq> -o <output_dir> [options]
```

See the MEGAHIT documentation for more details on usage and parameters.
