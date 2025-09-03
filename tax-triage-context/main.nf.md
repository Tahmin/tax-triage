# Main Pipeline Script: `main.nf`

## Overview
This is the main entry point for the nf-core/taxtriage pipeline, a Nextflow-based workflow for metagenomic taxonomic triage and analysis. It orchestrates the initialization, parameter validation, and execution of the primary workflow.

## Key Features
- **Pipeline Initialization:** Sets up the workflow environment, validates parameters, and prints a summary.
- **Workflow Inclusion:** Imports the main analysis workflow from `workflows/taxtriage.nf`.
- **Execution:** Defines and runs the `NFCORE_TAXTRIAGE` workflow, which in turn calls the `TAXTRIAGE` workflow.
- **Modular Design:** Uses Nextflow DSL2 for modularity and maintainability.

## Main Sections
- **Header and Metadata:** Copyright, licensing, and project links.
- **Parameter Handling:** (Commented) Example for genome parameter extraction.
- **Initialization:** Calls `WorkflowMain.initialise` to set up the pipeline.
- **Workflow Inclusion:**
  ```nextflow
  include { TAXTRIAGE } from './workflows/taxtriage'
  ```
- **Workflow Definition:**
  ```nextflow
  workflow NFCORE_TAXTRIAGE {
      TAXTRIAGE ()
  }
  ```
- **Workflow Execution:**
  ```nextflow
  workflow {
      NFCORE_TAXTRIAGE ()
  }
  ```

## Inputs
- Parameters and configuration files as defined in `params` and `nextflow.config`.

## Outputs
- All outputs are managed by the included `TAXTRIAGE` workflow.

## Usage
Run the pipeline with:
```bash
nextflow run main.nf -profile <profile> --input <samplesheet.csv> [other parameters]
```

## References
- [nf-core/taxtriage GitHub](https://github.com/nf-core/taxtriage)
- [nf-core website](https://nf-co.re/taxtriage)
- [Nextflow documentation](https://www.nextflow.io/)

---

This file is the orchestrator for the entire pipeline and should not require modification for standard usage. For workflow logic, see `workflows/taxtriage.nf` and the modules it includes.
