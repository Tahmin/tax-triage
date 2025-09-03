# report.nf

## Overview

The `report.nf` subworkflow generates summary reports from the results of the metagenomics pipeline. These reports provide insights into data quality, taxonomic composition, and other key metrics.

## Big Picture

Reporting is the final step, consolidating outputs from previous steps into user-friendly formats for interpretation and sharing.

## Detailed Workflow

1. **Input**: Receives results from classification, assembly, and other steps.
2. **Report generation**: Compiles results into summary tables, plots, or interactive reports.
3. **Output**: Produces reports for end users.

## Included Modules

**Exact module paths included:**

- ../../modules/local/alignment_per_sample
- ../../modules/local/report_merge

---

*Check `report.nf` for the exact reporting tools and formats used.*
