# Picard MarkDuplicates Module

## Big Picture
The `picard/markduplicates` module runs Picard's MarkDuplicates tool, which identifies and marks duplicate reads in sequencing data to improve downstream analysis accuracy.

## Main Files
- `main.nf`: Nextflow process definition for MarkDuplicates.
- `environment.yml`: Conda environment for Picard.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Aligned sequencing reads (SAM/BAM files).

## Outputs
- BAM files with duplicates marked, metrics files.

## Container/Conda Environment
- Defined in `environment.yml` (uses Picard tools).

## Use of bin Scripts
- Calls Picard MarkDuplicates directly; no custom bin script in this module.

## Script Section Explanation
- Runs Picard MarkDuplicates with user-specified parameters for duplicate marking.

---

# Example Command
```
picard MarkDuplicates I=<input.bam> O=<output.bam> M=<metrics.txt>
```

See the Picard documentation for more details on usage and parameters.
