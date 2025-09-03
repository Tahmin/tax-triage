# Gunzip Module

## Big Picture
The `gunzip` module decompresses gzipped files, preparing them for downstream analysis in the pipeline.

## Main Files
- `main.nf`: Nextflow process definition for gunzip.
- `environment.yml`: Conda environment for gunzip.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Gzipped files (e.g., .gz FASTQ, VCF, or other formats).

## Outputs
- Decompressed files (original format).

## Container/Conda Environment
- Defined in `environment.yml` (uses gunzip or equivalent tools).

## Use of bin Scripts
- Calls gunzip directly; no custom bin script in this module.

## Script Section Explanation
- Runs gunzip to decompress input files.

---

# Example Command
```
gunzip <input.gz>
```

See the gunzip documentation for more details on usage and parameters.
