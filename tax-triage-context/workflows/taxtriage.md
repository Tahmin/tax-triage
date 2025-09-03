# taxtriage.nf

## Overview

The `taxtriage.nf` workflow is the main entry point for the tax-triage metagenomics pipeline. It orchestrates the entire analysis, from input validation and quality control to host removal, classification, assembly, reporting, and final summary. The workflow is modular, leveraging both local and nf-core modules and subworkflows to process metagenomic sequencing data in a robust and reproducible manner.

## Big Picture (Simplified)

1. **Input Validation**: Checks and prepares input files (samplesheet or FASTQ).
2. **Quality Control**: Performs QC and optional trimming on reads.
3. **Host Removal**: Filters out host (e.g., human) reads.
4. **Classification**: Assigns taxonomy to reads using tools like Kraken2, Centrifuge, or MetaPhlAn.
5. **Reference Preparation**: Prepares or downloads reference genomes/databases as needed.
6. **Alignment & Assembly**: Aligns reads to references and assembles contigs.
7. **Reporting & Visualization**: Generates summary reports and visualizations (e.g., MultiQC, Krona).
8. **Completion**: Sends summary and optional email notification.

## Detailed Workflow Components

### 1. Input Validation
- Validates input parameters and files (samplesheet or FASTQ).
- Ensures required files exist and are in the correct format.
- Uses the `INPUT_CHECK` subworkflow.

### 2. Quality Control & Preprocessing
- Performs read QC with FastQC, Fastp, and/or Porechop/Trimgalore.
- Optionally compresses and trims reads.
- Downsamples reads if requested.
- Uses modules: `FASTQC`, `FASTP`, `TRIMGALORE`, `PORECHOP`, `BBMAP_BBNORM`, `COUNT_READS`, `PYCOQC`.

### 3. Host Removal
- Removes host reads using alignment (e.g., minimap2) or classification (e.g., Kraken2).
- Uses the `HOST_REMOVAL` subworkflow.

### 4. Classification
- Assigns taxonomy to reads using Kraken2, Centrifuge, or MetaPhlAn.
- Generates classification reports and Krona plots.
- Uses the `CLASSIFIER` subworkflow.

### 5. Reference Preparation
- Downloads or prepares reference genomes/databases.
- Indexes references for alignment.
- Uses the `REFERENCE_PREP` subworkflow and modules like `DOWNLOAD_DB`, `DOWNLOAD_PATHOGENS`, `DOWNLOAD_TAXDUMP`.

### 6. Alignment & Assembly
- Aligns reads to reference genomes.
- Assembles contigs from reads.
- Uses the `ALIGNMENT` and `ASSEMBLY` subworkflows.

### 7. Reporting & Visualization
- Generates summary reports (e.g., MultiQC, custom reports).
- Visualizes results (e.g., Krona, MultiQC, Nanoplot).
- Uses the `REPORT` subworkflow and modules like `MULTIQC`, `NANOPLOT`, `CUSTOM_DUMPSOFTWAREVERSIONS`.

### 8. Completion & Notification
- Sends a summary and optional email notification upon completion.
- Uses `NfcoreTemplate.email` and `NfcoreTemplate.summary`.

## Included Subworkflows and Modules

### Subworkflows
- `../subworkflows/local/input_check`
- `../subworkflows/local/alignment`
- `../subworkflows/local/report`
- `../subworkflows/local/filter_reads`
- `../subworkflows/local/host_removal`
- `../subworkflows/local/reference_prep`
- `../subworkflows/local/assembly`
- `../subworkflows/local/classifier`

### Key Modules
- `../modules/nf-core/fastqc/main`
- `../modules/nf-core/fastp/main`
- `../modules/nf-core/trimgalore/main`
- `../modules/nf-core/porechop/main`
- `../modules/nf-core/bbmap/bbnorm/main`
- `../modules/nf-core/pycoqc/main`
- `../modules/nf-core/multiqc/main`
- `../modules/nf-core/pigz/compress/main`
- `../modules/nf-core/seqtk/sample/main`
- `../modules/nf-core/artic/guppyplex/main`
- `../modules/nf-core/nanoplot/main`
- `../modules/nf-core/custom/dumpsoftwareversions/main`
- `../modules/local/*` (custom modules for download, mapping, merging, etc.)

## Notes
- The workflow is highly configurable via parameters (e.g., classifier choice, reference sources, QC options).
- Supports both local and cloud execution, with containerization (Docker/Singularity).
- Designed for robust, reproducible, and scalable metagenomics analysis.

---

*For more details, see the code and comments in `workflows/taxtriage.nf` and the documentation for each subworkflow and module.*
