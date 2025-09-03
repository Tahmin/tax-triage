# ARTIC GUPPYPLEX Module

## Big Picture
The `artic/guppyplex` module is part of the ARTIC pipeline for viral genome analysis. It demultiplexes Oxford Nanopore sequencing reads using Guppy, filtering and organizing reads for downstream analysis.

## Main Files
- `main.nf`: Nextflow process definition for guppyplex.
- `meta.yml`: Module metadata.

## Inputs
- Typically, raw Nanopore sequencing reads (FASTQ files) and barcode information.

## Outputs
- Demultiplexed and filtered FASTQ files, ready for downstream ARTIC analysis.

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Guppy or MinKNOW container/environment.

## Use of bin Scripts
- May call Guppy or related demultiplexing tools directly; no custom bin script in this module.

## Script Section Explanation
- Runs Guppyplex to demultiplex and filter reads based on barcodes and quality.

---

# Example Command
```
guppy_barcoder --input_path <input_dir> --save_path <output_dir> [options]
```

See the ARTIC pipeline documentation for more details on usage and parameters.
