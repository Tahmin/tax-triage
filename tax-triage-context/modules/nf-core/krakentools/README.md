# KrakenTools Modules

This directory contains modules for working with KrakenTools, a suite of scripts for post-processing Kraken and Kraken2 output files.

---

## combinekreports
- **Purpose:** Combines multiple Kraken report files into a single summary report.
- **Main Files:**
  - `main.nf`: Nextflow process for combining reports.
  - `meta.yml`: Module metadata.
- **Inputs:** Kraken report files.
- **Outputs:** Combined summary report.

## kreport2krona
- **Purpose:** Converts Kraken report files to Krona-compatible format for visualization.
- **Main Files:**
  - `main.nf`: Nextflow process for conversion.
  - `meta.yml`: Module metadata.
- **Inputs:** Kraken report files.
- **Outputs:** Krona-compatible files.

---

## Container/Conda Environment
- Defined in the module or inherited from the pipeline.

## Use of bin Scripts
- Modules call KrakenTools scripts directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate KrakenTools script for its function (e.g., `combine_kreports.py`, `kreport2krona.py`).

---

# Example Commands
```
combine_kreports.py -r <report1> -r <report2> -o <combined_report.txt>
kreport2krona.py -r <report.txt> -o <krona.txt>
```

See the KrakenTools documentation for more details on usage and parameters.
