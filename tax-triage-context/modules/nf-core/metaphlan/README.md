# MetaPhlAn Modules

This directory contains modules for working with MetaPhlAn, a tool for profiling the composition of microbial communities from metagenomic sequencing data.

---

## makedb
- **Purpose:** Builds MetaPhlAn marker gene databases.
- **Main Files:**
  - `main.nf`: Nextflow process for database building.
  - `meta.yml`: Module metadata.
- **Inputs:** Marker gene sequences or source data.
- **Outputs:** MetaPhlAn database files.

## metaphlan
- **Purpose:** Profiles microbial community composition from metagenomic reads.
- **Main Files:**
  - `main.nf`: Nextflow process for profiling.
  - `meta.yml`: Module metadata.
- **Inputs:** Sequencing reads (FASTQ files), MetaPhlAn database.
- **Outputs:** Taxonomic profiles (tabular or standard MetaPhlAn output).

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call MetaPhlAn tools directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate MetaPhlAn command for its function (e.g., `metaphlan`, `metaphlan_db_builder.py`).

---

# Example Commands
```
metaphlan <reads.fq> --input_type fastq -o <output.txt>
metaphlan_db_builder.py <marker_genes.fa> -o <db_dir>
```

See the MetaPhlAn documentation for more details on usage and parameters.
