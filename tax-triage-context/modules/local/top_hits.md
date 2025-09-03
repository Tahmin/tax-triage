# TOP_HITS Module

## Big Picture
The `TOP_HITS` module identifies top taxonomic hits from classification reports, generating summary tables and lists for downstream analysis.

## Process Name
`TOP_HITS`

## Container/Conda Environment
- **Conda:** `bioconda::pysam` (if enabled)
- **Container:**
  - Singularity: `library://bmerritt1762/jhuaplbio/reportlab-pdf:4.0.7`
  - Docker: `jhuaplbio/reportlab-pdf:4.0.7`

## Inputs
- `tuple val(meta), path(report), path(distributions), path(pathogens)`: Metadata, report file, distributions, and pathogens file.

## Outputs
- `path "versions.yml"` (emit: versions): YAML file with version information.
- `tuple val(meta), path("*top_report.tsv")` (emit: tops, optional): Top hits summary table.
- `tuple val(meta), path("*toptaxids.txt")` (emit: taxids, optional): Top taxids list.
- `tuple val(meta), path("*topnames.txt")` (emit: names, optional): Top names list.
- `tuple val(meta), path("*.krakenreport_mqc.tsv")` (emit: krakenreport, optional): MultiQC-compatible summary table.

## Use of bin Scripts
- Uses `get_top_hits.py` from the pipeline's `bin/` directory to identify top hits and generate summary tables.

## Script Section Explanation
- Runs `get_top_hits.py` with report, distributions, and pathogens file, then processes output with awk to generate summary tables and lists.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
get_top_hits.py -i <report> -o <top_report.tsv> [options]
awk ... <top_report.tsv> > <krakenreport_mqc.tsv>
awk ... <top_report.tsv> > <topnames.txt>
awk ... <top_report.tsv> > <toptaxids.txt>
```
