# Krona Modules

This directory contains modules for working with Krona, a tool for hierarchical data visualization, especially for metagenomics.

---

## kronadb
- **Purpose:** Downloads or prepares Krona taxonomy databases.
- **Main Files:**
  - `main.nf`: Nextflow process for Krona DB preparation.
  - `meta.yml`: Module metadata.
- **Inputs:** None or database source.
- **Outputs:** Krona taxonomy database files.

## ktimporttaxonomy
- **Purpose:** Imports taxonomy data into Krona for visualization.
- **Main Files:**
  - `main.nf`: Nextflow process for taxonomy import.
  - `meta.yml`: Module metadata.
- **Inputs:** Taxonomy data files.
- **Outputs:** Krona visualization files (HTML).

## ktimporttext
- **Purpose:** Imports text data into Krona for visualization.
- **Main Files:**
  - `main.nf`: Nextflow process for text import.
  - `meta.yml`: Module metadata.
- **Inputs:** Text data files.
- **Outputs:** Krona visualization files (HTML).

## ktupdatetaxonomy
- **Purpose:** Updates Krona taxonomy databases.
- **Main Files:**
  - `main.nf`: Nextflow process for taxonomy update.
  - `meta.yml`: Module metadata.
- **Inputs:** None or update source.
- **Outputs:** Updated Krona taxonomy database files.

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call Krona tools directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Krona command for its function (e.g., `ktImportTaxonomy`, `ktImportText`, `ktUpdateTaxonomy`).

---

# Example Commands
```
ktImportTaxonomy <taxonomy.txt> -o <output.html>
ktImportText <input.txt> -o <output.html>
ktUpdateTaxonomy
```

See the Krona documentation for more details on usage and parameters.
