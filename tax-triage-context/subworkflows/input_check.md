# input_check.nf

## Overview

The `input_check.nf` subworkflow validates input files and metadata before processing. This step ensures that all required data is present and correctly formatted.

## Big Picture

Input checking prevents pipeline failures and ensures reproducibility by catching errors early in the workflow.

## Detailed Workflow

1. **Input**: Receives raw data files and metadata.
2. **Validation**: Checks file existence, format, and consistency.
3. **Output**: Reports any issues or confirms readiness for processing.

## Included Modules

**Exact module paths included:**

- ../../modules/local/samplesheet_check
- ../../modules/local/samplesheet_generate

---

*See `input_check.nf` for the exact checks performed.*
