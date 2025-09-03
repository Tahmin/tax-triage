# KRONA Module

## Big Picture
The `KRONA` module generates interactive Krona plots (HTML) from taxonomy reports, allowing users to visually explore taxonomic composition in metagenomic samples.

## Process Name
`KRONA`

## Container/Conda Environment
- **Conda:** `bioconda::krona=2.7.1`
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/krona:2.7.1--pl526_5`
  - Docker: `biocontainers/krona:2.7.1--pl526_5`

## Inputs
- `tuple val(meta), path(report)`: Metadata and the taxonomy report file to be visualized.

## Outputs
- `path "*.html"` (emit: html): Krona interactive HTML plot.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- No custom bin script; uses `ktImportTaxonomy` from KronaTools.

## Script Section Explanation
- Runs `ktImportTaxonomy` to generate the Krona HTML plot.
- Captures KronaTools version information in `versions.yml`.

---

# Example Command
```
ktImportTaxonomy <input_report> -tax taxonomy
```
