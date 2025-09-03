# RSeQC BamStat Module

## Big Picture
The `rseqc/bamstat` module runs BamStat from RSeQC, a tool for quality control and statistics on BAM files from RNA-seq experiments.

## Main Files
- `main.nf`: Nextflow process definition for BamStat.
- `meta.yml`: Module metadata.

## Inputs
- Aligned RNA-seq reads (BAM files).

## Outputs
- BAM statistics reports (text or tabular format).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses an RSeQC container/environment.

## Use of bin Scripts
- Calls BamStat directly; no custom bin script in this module.

## Script Section Explanation
- Runs BamStat with user-specified parameters for BAM QC.

---

# Example Command
```
bam_stat.py -i <input.bam> -o <output.txt>
```

See the RSeQC documentation for more details on usage and parameters.
