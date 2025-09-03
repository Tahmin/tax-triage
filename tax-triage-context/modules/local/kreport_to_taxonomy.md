# KREPORT_TO_TAXONOMY Module

## Big Picture
The `KREPORT_TO_TAXONOMY` module converts Kraken classification reports into NCBI taxonomy files (`nodes.dmp` and `names.dmp`). This enables downstream tools to use the classification results in a standardized taxonomy format.

## Process Name
`KREPORT_TO_TAXONOMY`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/biopython:1.78`
  - Docker: `biocontainers/biopython:1.75`

## Inputs
- `tuple val(meta), path(report)`: Metadata and the Kraken report file to be converted.

## Outputs
- `path "versions.yml"` (emit: versions): YAML file with version information.
- `tuple val(meta), path("*nodes.dmp")` (emit: nodes): NCBI taxonomy nodes file.
- `tuple val(meta), path("*names.dmp")` (emit: names): NCBI taxonomy names file.

## Use of bin Scripts
- Uses `create_taxonomy.py` from the pipeline's `bin/` directory to generate taxonomy files from the Kraken report.

## Script Section Explanation
- Echoes the sample ID and a start message.
- Creates a `taxonomy` directory.
- Runs `create_taxonomy.py` to generate `nodes.dmp` and `names.dmp`.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
create_taxonomy.py --nodes nodes.dmp --names names.dmp --report <input_report>
```
