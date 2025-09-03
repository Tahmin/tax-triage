# BBMAP BBNORM Module

## Big Picture
The `bbmap/bbnorm` module normalizes sequencing read coverage using BBnorm from the BBMap suite, reducing coverage bias and improving downstream assembly or analysis.

## Main Files
- `main.nf`: Nextflow process definition for BBnorm.
- `environment.yml`: Conda environment for BBnorm.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- High-coverage sequencing reads (FASTQ files).

## Outputs
- Normalized FASTQ files with reduced coverage bias.

## Container/Conda Environment
- Defined in `environment.yml` (uses BBMap/BBnorm tools).

## Use of bin Scripts
- Calls BBnorm directly; no custom bin script in this module.

## Script Section Explanation
- Runs BBnorm to normalize read coverage, with parameters for target coverage and minimum depth.

---

# Example Command
```
bbnorm.sh in=<input.fastq> out=<output.fastq> target=<coverage> min=<min_depth>
```

See the BBMap documentation for more details on usage and parameters.
