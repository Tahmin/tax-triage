# MAP_LOCAL_ASSEMBLY_TO_FASTA Module

## Big Picture
The `MAP_LOCAL_ASSEMBLY_TO_FASTA` module matches local assembly FASTA files to reference assemblies, producing mapping and accession outputs for downstream analysis.

## Process Name
`MAP_LOCAL_ASSEMBLY_TO_FASTA`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `docker://pegi3s/biopython:latest`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), path(fasta)`: Metadata and the FASTA file to be mapped.
- `path(assembly)`: Reference assembly file.
- `path(pathogens_file)`: Optional pathogens file for filtering.

## Outputs
- `tuple val(meta), path("*localmap.tsv")` (emit: map): Mapping results.
- `tuple val(meta), path("*output.gcfids.txt")` (emit: accessions): List of matched GCF accessions.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `fuzzy_match_assembly.py` from the pipeline's `bin/` directory to perform the mapping.

## Script Section Explanation
- Runs `fuzzy_match_assembly.py` with the provided FASTA, assembly, and optional pathogens file.
- Extracts GCF accessions from the mapping output.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
fuzzy_match_assembly.py -i <fasta> -a <assembly> -o <output.tsv> [-p <pathogens_file>]
cut -f 2 <output.tsv> > <output.gcfids.txt>
```
