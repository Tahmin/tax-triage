# Trimmomatic Module

## Big Picture
The `trimmomatic` module runs Trimmomatic, a tool for flexible read trimming and quality filtering of Illumina NGS data.

## Main Files
- `main.nf`: Nextflow process definition for Trimmomatic.
- `meta.yml`: Module metadata.

## Inputs
- Raw Illumina sequencing reads (FASTQ files).

## Outputs
- Trimmed FASTQ files, log files.

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Trimmomatic container/environment.

## Use of bin Scripts
- Calls Trimmomatic directly; no custom bin script in this module.

## Script Section Explanation
- Runs Trimmomatic with user-specified parameters for trimming and filtering.

---

# Example Command
```
trimmomatic PE <input_R1.fq> <input_R2.fq> <output_R1_paired.fq> <output_R1_unpaired.fq> <output_R2_paired.fq> <output_R2_unpaired.fq> [options]
```

See the Trimmomatic documentation for more details on usage and parameters.
