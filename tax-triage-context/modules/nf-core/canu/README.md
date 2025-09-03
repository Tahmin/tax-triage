# CANU Module

## Big Picture
The `canu` module runs Canu, a tool for de novo assembly of long noisy reads, such as those from PacBio or Oxford Nanopore.

## Main Files
- `main.nf`: Nextflow process definition for Canu.
- `environment.yml`: Conda environment for Canu.
- `meta.yml`: Module metadata.

## Inputs
- Long-read sequencing data (FASTQ files).

## Outputs
- Assembled contigs (FASTA files) and assembly reports.

## Container/Conda Environment
- Defined in `environment.yml` (uses Canu tools).

## Use of bin Scripts
- Calls Canu directly; no custom bin script in this module.

## Script Section Explanation
- Runs Canu with user-specified parameters for genome assembly.

---

# Example Command
```
canu -p <prefix> -d <output_dir> genomeSize=<size> -nanopore <reads.fastq>
```

See the Canu documentation for more details on usage and parameters.
