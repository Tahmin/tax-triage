# PULL_FASTA Module

## Big Picture
The `PULL_FASTA` module retrieves reference FASTA sequences for specified taxids and genomes, preparing them for downstream analysis.

## Process Name
`PULL_FASTA`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), path(taxid_file), path(genomes)`: Metadata, taxid file, and genomes file.

## Outputs
- `tuple val(meta), path("*${meta.id}.fasta")` (emit: fasta): Retrieved FASTA file (optional).

## Use of bin Scripts
- Uses `getfasta_refs.py` from the pipeline's `bin/` directory to retrieve FASTA sequences.

## Script Section Explanation
- Runs `getfasta_refs.py` with the provided taxid file and genomes file, outputting to the current directory.

---

# Example Command
```
getfasta_refs.py -i <taxid_file> -o <outdir> -t file -r <genomes> -q -p <meta.id>
```
