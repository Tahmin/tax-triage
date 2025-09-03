# SPLIT_VCF Module

## Big Picture
The `SPLIT_VCF` module splits VCF files into separate gzipped VCFs for downstream analysis, using mapping information if provided.

## Process Name
`SPLIT_VCF`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3 pysam` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/pysam:0.21.0--py39hcada746_1`
  - Docker: `biocontainers/pysam:0.21.0--py39hcada746_1`

## Inputs
- `tuple val(meta), path(vcf), path(tbi)`: Metadata, VCF file, and index file.

## Outputs
- `tuple val(meta), path("*vcf.gz")` (emit: vcfs, optional): Split gzipped VCF files.
- `path "versions.yml"` (emit: versions): YAML file with version information.

## Use of bin Scripts
- Uses `split_vcf.py` from the pipeline's `bin/` directory to split VCF files.

## Script Section Explanation
- Runs `split_vcf.py` with the input VCF file, outputs split gzipped VCFs.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
split_vcf.py -i <vcf> -o <output_prefix>
```
