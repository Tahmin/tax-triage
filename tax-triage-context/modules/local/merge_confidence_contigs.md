# METRIC_MERGE Module

## Big Picture
The `METRIC_MERGE` module merges confidence metrics from assemblies, producing a comprehensive metrics table for downstream analysis.

## Process Name
`METRIC_MERGE`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3 pysam` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/pysam:0.21.0--py39hcada746_1`
  - Docker: `biocontainers/pysam:0.21.0--py39hcada746_1`

## Inputs
- `tuple val(meta), path(single_metric)`: Metadata and single metric file to be merged.

## Outputs
- `tuple val(meta), path("*.fullmetrics.tsv")` (emit: metrics): Merged metrics table.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `merge_assemblies_conf.py` from the pipeline's `bin/` directory to merge metrics.

## Script Section Explanation
- Runs `merge_assemblies_conf.py` with the single metric file.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
merge_assemblies_conf.py -i <single_metric> -o <output.tsv>
```
