# MetaPhlAn3 Module

## Big Picture
The `metaphlan3/metaphlan3` module runs MetaPhlAn 3, a tool for profiling the composition of microbial communities from metagenomic sequencing data using clade-specific marker genes.

## Main Files
- `main.nf`: Nextflow process definition for MetaPhlAn 3.
- `meta.yml`: Module metadata.

## Inputs
- Sequencing reads (FASTQ files).
- MetaPhlAn 3 database.

## Outputs
- Taxonomic profiles (tabular or standard MetaPhlAn 3 output).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a MetaPhlAn 3 container/environment.

## Use of bin Scripts
- Calls MetaPhlAn 3 directly; no custom bin script in this module.

## Script Section Explanation
- Runs MetaPhlAn 3 with user-specified parameters for taxonomic profiling.

---

# Example Command
```
metaphlan <reads.fq> --input_type fastq -o <output.txt>
```

See the MetaPhlAn 3 documentation for more details on usage and parameters.
