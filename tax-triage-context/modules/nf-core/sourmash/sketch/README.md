# Sourmash Sketch Module

## Big Picture
The `sourmash/sketch` module runs Sourmash to compute MinHash sketches of DNA, RNA, or protein sequences for fast similarity searches and comparisons.

## Main Files
- `main.nf`: Nextflow process definition for Sourmash sketch.
- `environment.yml`: Conda environment for Sourmash.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Sequence files (FASTA, FASTQ, etc.).

## Outputs
- Sourmash signature files (.sig).

## Container/Conda Environment
- Defined in `environment.yml` (uses Sourmash tools).

## Use of bin Scripts
- Calls Sourmash directly; no custom bin script in this module.

## Script Section Explanation
- Runs Sourmash with user-specified parameters to compute MinHash sketches.

---

# Example Command
```
sourmash sketch dna <input.fa> -o <output.sig>
```

See the Sourmash documentation for more details on usage and parameters.
