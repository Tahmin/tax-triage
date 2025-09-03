# Centrifuge Module

## Big Picture
The `centrifuge/centrifuge` module runs Centrifuge, a tool for rapid and sensitive classification of metagenomic sequences.

## Main Files
- `main.nf`: Nextflow process definition for Centrifuge.

## Inputs
- Sequencing reads (FASTQ files).
- Centrifuge database.

## Outputs
- Classification results (tabular or standard Centrifuge output).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Centrifuge container/environment.

## Use of bin Scripts
- Calls Centrifuge directly; no custom bin script in this module.

## Script Section Explanation
- Runs Centrifuge with user-specified parameters for metagenomic classification.

---

# Example Command
```
centrifuge -x <db> -U <reads.fq> -S <output.txt> [options]
```

See the Centrifuge documentation for more details on usage and parameters.
