# Pigz Compress Module

## Big Picture
The `pigz/compress` module compresses files using pigz, a parallel implementation of gzip, to speed up compression for large datasets.

## Main Files
- `main.nf`: Nextflow process definition for pigz compression.
- `environment.yml`: Conda environment for pigz.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Files to be compressed (e.g., FASTQ, BAM, or other formats).

## Outputs
- Compressed files (.gz).

## Container/Conda Environment
- Defined in `environment.yml` (uses pigz tools).

## Use of bin Scripts
- Calls pigz directly; no custom bin script in this module.

## Script Section Explanation
- Runs pigz to compress input files in parallel.

---

# Example Command
```
pigz <input.file>
```

See the pigz documentation for more details on usage and parameters.
