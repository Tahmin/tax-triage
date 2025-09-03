# Porechop Module

## Big Picture
The `porechop` module runs Porechop, a tool for adapter trimming of Oxford Nanopore reads.

## Main Files
- `main.nf`: Nextflow process definition for Porechop.
- `meta.yml`: Module metadata.

## Inputs
- Oxford Nanopore sequencing reads (FASTQ files).

## Outputs
- Adapter-trimmed FASTQ files.

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Porechop container/environment.

## Use of bin Scripts
- Calls Porechop directly; no custom bin script in this module.

## Script Section Explanation
- Runs Porechop with user-specified parameters for adapter trimming.

---

# Example Command
```
porechop -i <input.fastq> -o <output.fastq>
```

See the Porechop documentation for more details on usage and parameters.
