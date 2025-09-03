# DIAMOND Modules

This directory contains modules for working with DIAMOND, a fast sequence aligner for protein and translated DNA searches.

---

## blastx
- **Purpose:** Runs DIAMOND BLASTX to align DNA reads against a protein database.
- **Main Files:**
  - `main.nf`: Nextflow process for BLASTX.
  - `environment.yml`: Conda environment for DIAMOND BLASTX.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** DNA reads (FASTA/FASTQ), protein database.
- **Outputs:** BLASTX alignment results.

## makedb
- **Purpose:** Builds a DIAMOND protein database from input protein sequences.
- **Main Files:**
  - `main.nf`: Nextflow process for database creation.
  - `environment.yml`: Conda environment for DIAMOND makedb.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** Protein sequences (FASTA).
- **Outputs:** DIAMOND database files.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml`).

## Use of bin Scripts
- Modules call DIAMOND commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate DIAMOND command for its function (e.g., `diamond blastx`, `diamond makedb`).

---

# Example Commands
```
diamond blastx -d <db.dmnd> -q <reads.fq> -o <output.txt>
diamond makedb --in <proteins.faa> -d <db.dmnd>
```

See the DIAMOND documentation for more details on usage and parameters.
