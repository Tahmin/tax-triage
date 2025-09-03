# ORGANISM_MERGE_REPORT Module

## Big Picture
The `ORGANISM_MERGE_REPORT` module generates organism-level reports (TXT and PDF) by merging pathogen files and distributions, with options for filtering and customizing the report.

## Process Name
`ORGANISM_MERGE_REPORT`

## Container/Conda Environment
- **Conda:** `bioconda::pysam` (if enabled)
- **Container:**
  - Singularity: `docker://quay.io/jhuaplbio/reportlab-pdf:4.0.8`
  - Docker: `jhuaplbio/reportlab-pdf:4.0.8`

## Inputs
- `tuple val(meta), file(files_of_pathogens), file(distributions)`: Metadata, pathogen files, and distributions.
- `val(missing_samples)`: List of missing samples.
- `path(nodes)`: Taxonomy nodes file.

## Outputs
- `path "versions.yml"` (emit: versions): YAML file with version information.
- `path("*organisms.report.txt")` (emit: report): Organism report (TXT, optional).
- `path("*organisms.report.pdf")` (emit: pdf): Organism report (PDF).

## Use of bin Scripts
- Uses `create_report.py` from the pipeline's `bin/` directory to generate reports.

## Script Section Explanation
- Runs `create_report.py` with pathogen files, distributions, and various options to generate TXT and PDF reports.
- Captures awk version information in `versions.yml`.

---

# Example Command
```
create_report.py -i <files_of_pathogens> -u <output_txt> -o <output_pdf> [options]
```
