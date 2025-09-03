# visualize_reports.nf

## Overview

The `visualize_reports.nf` subworkflow creates visualizations from pipeline results, such as taxonomic profiles, diversity plots, or assembly statistics.

## Big Picture

Visualization helps interpret complex metagenomic data and communicate findings effectively.

## Detailed Workflow

1. **Input**: Receives processed results and summary reports.
2. **Visualization**: Generates plots and figures (e.g., barplots, heatmaps).
3. **Output**: Produces visual outputs for reports or presentations.

## Included Modules

**Exact module paths included:**

- ../../modules/nf-core/krona/ktimporttaxonomy/main
- ../../modules/nf-core/krona/ktimporttext/main
- ../../modules/nf-core/krakentools/kreport2krona/main

---

*See `visualize_reports.nf` for the specific visualization methods used.*
