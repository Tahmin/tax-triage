# PycoQC Module

## Big Picture
The `pycoqc` module runs PycoQC, a tool for interactive quality control of Oxford Nanopore sequencing data.

## Main Files
- `main.nf`: Nextflow process definition for PycoQC.
- `meta.yml`: Module metadata.

## Inputs
- Oxford Nanopore sequencing summary files (and optionally, FASTQ files).

## Outputs
- Quality control reports (HTML, JSON, plots).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a PycoQC container/environment.

## Use of bin Scripts
- Calls PycoQC directly; no custom bin script in this module.

## Script Section Explanation
- Runs PycoQC with user-specified parameters for QC and visualization.

---

# Example Command
```
pycoQC -f <sequencing_summary.txt> -o <output.html>
```

See the PycoQC documentation for more details on usage and parameters.
