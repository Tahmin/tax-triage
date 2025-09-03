# SAMPLESHEET_CHECK Module

## Big Picture
The `SAMPLESHEET_CHECK` module validates a samplesheet CSV file, ensuring it meets pipeline requirements and outputs a validated CSV for downstream analysis.

## Process Name
`SAMPLESHEET_CHECK`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/python:3.9--1`
  - Docker: `biocontainers/python:3.8.3`

## Inputs
- `path samplesheet`: Samplesheet CSV file to be validated.

## Outputs
- `path '*.csv'` (emit: csv): Validated samplesheet CSV.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `check_samplesheet.py` from the pipeline's `bin/` directory to validate the samplesheet.

## Script Section Explanation
- Runs `check_samplesheet.py` with the input samplesheet and outputs a validated CSV.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
check_samplesheet.py <samplesheet> samplesheet.valid.csv
```
