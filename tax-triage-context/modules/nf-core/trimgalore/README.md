# TrimGalore Module

## Big Picture
The `trimgalore` module runs TrimGalore, a wrapper tool for quality and adapter trimming of sequencing reads using Cutadapt and FastQC.

## Main Files
- `main.nf`: Nextflow process definition for TrimGalore.
- `meta.yml`: Module metadata.

## Inputs
- Raw sequencing reads (FASTQ files).

## Outputs
- Trimmed FASTQ files, quality reports (HTML, TXT).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a TrimGalore container/environment.

## Use of bin Scripts
- Calls TrimGalore directly; no custom bin script in this module.

## Script Section Explanation
- Runs TrimGalore with user-specified parameters for trimming and QC.

---

# Example Command
```
trim_galore <input.fastq> [options]
```

See the TrimGalore documentation for more details on usage and parameters.
