# NCBI Genome Download Module

## Big Picture
The `ncbigenomedownload` module downloads genome data from NCBI, automating the retrieval of reference genomes for downstream analysis.

## Main Files
- `main.nf`: Nextflow process definition for NCBI genome download.
- `environment.yml`: Conda environment for genome download.
- `meta.yml`: Module metadata.

## Inputs
- Genome accession numbers or organism names.

## Outputs
- Downloaded genome files (FASTA, GFF, etc.).

## Container/Conda Environment
- Defined in `environment.yml` (uses ncbi-genome-download or similar tools).

## Use of bin Scripts
- Calls ncbi-genome-download directly; no custom bin script in this module.

## Script Section Explanation
- Runs ncbi-genome-download with user-specified parameters for genome retrieval.

---

# Example Command
```
ncbi-genome-download bacteria -o <output_dir> -l complete -F fasta <accession>
```

See the ncbi-genome-download documentation for more details on usage and parameters.
