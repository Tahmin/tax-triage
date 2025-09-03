# MultiQC Module

## Big Picture
The `multiqc` module runs MultiQC, a tool for aggregating results from bioinformatics analyses across many samples into a single report.

## Main Files
- `main.nf`: Nextflow process definition for MultiQC.
- `environment.yml`: Conda environment for MultiQC.
- `meta.yml`: Module metadata.
- `tests/`: Test files for module validation.

## Inputs
- Output files from various bioinformatics tools (e.g., FastQC, samtools, etc.).

## Outputs
- MultiQC report (HTML, data files).

## Container/Conda Environment
- Defined in `environment.yml` (uses MultiQC tools).

## Use of bin Scripts
- Calls MultiQC directly; no custom bin script in this module.

## Script Section Explanation
- Runs MultiQC to aggregate and visualize results from multiple tools.

---

# Example Command
```
multiqc <input_dir> -o <output_dir>
```

See the MultiQC documentation for more details on usage and parameters.
