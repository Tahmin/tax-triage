# PULL_FASTA Module (Kraken)

## Big Picture
The `PULL_FASTA` module (Kraken) retrieves filtered FASTQ and reference FASTA sequences for specified taxids and classified reads, preparing them for downstream analysis.

## Process Name
`PULL_FASTA`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), val(taxid_file), val(classified_reads), val(classified_reads_assignment), val(genomes)`: Metadata, taxid file, classified reads, assignment, and genomes.

## Outputs
- `tuple val(meta), path("*filtered.fastq"), path("*refs.fasta")` (emit: fastq): Filtered FASTQ and reference FASTA files.

## Use of bin Scripts
- Uses `getfasta_refs.py` from the pipeline's `bin/` directory to retrieve FASTA and filtered FASTQ sequences.

## Script Section Explanation
- Runs `getfasta_refs.py` with the provided taxid file, classified reads, assignment, and genomes, outputting filtered FASTQ and reference FASTA files.

---

# Example Command
```
getfasta_refs.py -i <taxid_file> -o <outfile> -t file -r <genomes> -d <classifieds> -a <classified_reads_assignment> -q
```
