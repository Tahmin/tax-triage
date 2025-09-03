# BLASTN Module

## Big Picture
The `blast/blastn` module runs BLASTN, a nucleotide-nucleotide sequence alignment tool, for comparing nucleotide sequences to sequence databases and finding regions of similarity.

## Main Files
- `main.nf`: Nextflow process definition for BLASTN.
- `meta.yml`: Module metadata.

## Inputs
- Query nucleotide sequences (FASTA files).
- Reference database.

## Outputs
- BLASTN alignment results (tabular or standard BLAST output).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a BLAST+ container/environment.

## Use of bin Scripts
- Calls BLASTN directly; no custom bin script in this module.

## Script Section Explanation
- Runs BLASTN with user-specified parameters for sequence alignment.

---

# Example Command
```
blastn -query <input.fa> -db <database> -out <output.txt> [options]
```

See the BLAST+ documentation for more details on usage and parameters.
