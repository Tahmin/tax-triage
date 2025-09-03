# Samtools Modules

This directory contains modules for working with Samtools, a suite of programs for interacting with high-throughput sequencing data in SAM, BAM, and CRAM formats.

---

## coverage
- **Purpose:** Computes coverage statistics from BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for coverage calculation.
  - `environment.yml`: Conda environment for Samtools.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** Coverage statistics.

## depth
- **Purpose:** Computes depth of coverage at each position in BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for depth calculation.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** Depth statistics.

## faidx
- **Purpose:** Indexes FASTA files.
- **Main Files:**
  - `main.nf`: Nextflow process for FASTA indexing.
  - `meta.yml`: Module metadata.
- **Inputs:** FASTA files.
- **Outputs:** Index files (.fai).

## fastq
- **Purpose:** Converts BAM files to FASTQ format.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM to FASTQ conversion.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** FASTQ files.

## index
- **Purpose:** Indexes BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM indexing.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** Index files (.bai).

## merge
- **Purpose:** Merges multiple BAM files into one.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM merging.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** Merged BAM file.

## sort
- **Purpose:** Sorts BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM sorting.
  - `environment.yml`: Conda environment for Samtools.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** BAM files.
- **Outputs:** Sorted BAM files.

## stats
- **Purpose:** Computes statistics on BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for BAM statistics.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** BAM files.
- **Outputs:** Statistics reports.

## view
- **Purpose:** Views and filters BAM files.
- **Main Files:**
  - `main.nf`: Nextflow process for viewing/filtering.
  - `meta.yml`: Module metadata.
- **Inputs:** BAM files.
- **Outputs:** Filtered BAM files or text output.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml` where present).

## Use of bin Scripts
- Modules call Samtools commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate Samtools command for its function (e.g., `samtools coverage`, `samtools depth`, `samtools faidx`, `samtools fastq`, `samtools index`, `samtools merge`, `samtools sort`, `samtools stats`, `samtools view`).

---

# Example Commands
```
samtools coverage <input.bam>
samtools depth <input.bam>
samtools faidx <input.fa>
samtools fastq <input.bam>
samtools index <input.bam>
samtools merge -o <merged.bam> <input1.bam> <input2.bam>
samtools sort <input.bam> -o <sorted.bam>
samtools stats <input.bam>
samtools view <input.bam> [options]
```

See the Samtools documentation for more details on usage and parameters.
