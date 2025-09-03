# NanoPlot Module

## Big Picture
The `nanoplot` module runs NanoPlot, a tool for visualization and quality control of Oxford Nanopore sequencing data.

## Main Files
- `main.nf`: Nextflow process definition for NanoPlot.
- `meta.yml`: Module metadata.

## Inputs
- Oxford Nanopore sequencing reads (FASTQ files).

## Outputs
- Quality control plots and summary statistics (HTML, PNG, TXT, etc.).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a NanoPlot container/environment.

## Use of bin Scripts
- Calls NanoPlot directly; no custom bin script in this module.

## Script Section Explanation
- Runs NanoPlot with user-specified parameters for QC and visualization.

---

# Example Command
```
NanoPlot --fastq <reads.fq> --outdir <output_dir> [options]
```

See the NanoPlot documentation for more details on usage and parameters.
