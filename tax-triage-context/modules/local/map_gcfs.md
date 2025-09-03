# MAP_GCF Module

## Big Picture
The `MAP_GCF` module maps FASTA files to reference assemblies, producing mapping tables for downstream analysis. It is typically used to associate contigs or sequences with their corresponding GCF accessions.

## Process Name
`MAP_GCF`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(fasta)`: Metadata and FASTA file to be mapped.
- `path(assembly)`: Reference assembly file.

## Outputs
- `tuple val(meta), path("*.mapping.tsv")` (emit: map): Mapping results.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `make_gcf_mapping.sh` from the pipeline's `bin/` directory to perform the mapping.

## Script Section Explanation
- Runs `make_gcf_mapping.sh` with the provided FASTA and assembly files.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
make_gcf_mapping.sh -i <fasta> -o <output.tsv> -a <assembly>
```
