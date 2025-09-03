# KRAKENREPORT Module

## Big Picture
The `KRAKENREPORT` module processes Kraken classification reports to generate MultiQC-compatible summary tables. It is used to convert raw Kraken output into a standardized TSV format for downstream analysis and reporting.

## Process Name
`KRAKENREPORT`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), path(report)`: Metadata and the Kraken report file to be processed.

## Outputs
- `path "versions.yml"` (emit: versions): YAML file with version information.
- `tuple val(meta), path("*.krakenreport_mqc.tsv")` (emit: krakenreport): MultiQC-compatible summary table.

## Use of bin Scripts
- Uses `krakenreport.py` from the pipeline's `bin/` directory to process the Kraken report.

## Script Section Explanation
- Echoes the sample ID and a start message.
- Runs `krakenreport.py` to generate the summary TSV.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
krakenreport.py -o <sample>.krakenreport_mqc.tsv -i <input_report> -d <sample_id>
```
