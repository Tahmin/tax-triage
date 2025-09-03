# Taxpasta Modules

This directory contains modules for working with Taxpasta, a tool for merging and standardizing taxonomic profiles from various metagenomics classifiers.

---

## merge
- **Purpose:** Merges multiple taxonomic profile files into a single standardized table.
- **Main Files:**
  - `main.nf`: Nextflow process for merging profiles.
  - `environment.yml`: Conda environment for Taxpasta.
  - `meta.yml`: Module metadata.
- **Inputs:** Taxonomic profile files (e.g., from Kraken, MetaPhlAn, etc.).
- **Outputs:** Merged and standardized taxonomic table.

## standardise
- **Purpose:** Standardizes a single taxonomic profile file to a common format.
- **Main Files:**
  - `main.nf`: Nextflow process for standardization.
  - `environment.yml`: Conda environment for Taxpasta.
  - `meta.yml`: Module metadata.
- **Inputs:** Taxonomic profile file.
- **Outputs:** Standardized taxonomic table.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml`).

## Use of bin Scripts
- Modules call Taxpasta commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Taxpasta command for its function (e.g., `taxpasta merge`, `taxpasta standardise`).

---

# Example Commands
```
taxpasta merge -i <profile1.tsv> <profile2.tsv> -o <merged.tsv>
taxpasta standardise -i <profile.tsv> -o <standardized.tsv>
```

See the Taxpasta documentation for more details on usage and parameters.
