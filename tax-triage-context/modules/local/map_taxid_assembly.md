# MAP_TAXID_ASSEMBLY Module

## Big Picture
The `MAP_TAXID_ASSEMBLY` module merges taxonomic IDs with assembly information, producing a merged taxid table for downstream analysis.

## Process Name
`MAP_TAXID_ASSEMBLY`

## Container/Conda Environment
- **Conda:** `bioconda::pysam` (if enabled)
- **Container:**
  - Singularity: `library://bmerritt1762/jhuaplbio/reportlab-pdf:4.0.7`
  - Docker: `jhuaplbio/reportlab-pdf:4.0.7`

## Inputs
- `tuple val(meta), file(gcfmapping)`: Metadata and GCF mapping file.
- `file(assembly)`: Reference assembly file.

## Outputs
- `tuple val(meta), path("*merged.taxid.tsv")` (emit: taxidmerged): Merged taxid table.

## Use of bin Scripts
- Uses `append_taxid.py` from the pipeline's `bin/` directory to merge taxids with assemblies.

## Script Section Explanation
- Runs `append_taxid.py` with the GCF mapping and assembly files.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
append_taxid.py -i <gcfmapping> -r <assembly> -o <output.tsv>
```
