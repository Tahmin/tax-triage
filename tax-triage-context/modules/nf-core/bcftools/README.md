# BCFTools Modules

This directory contains several modules for working with BCFtools, a suite for variant calling and manipulation of VCF/BCF files. Each submodule provides a specific function in variant analysis workflows.

---

## consensus
- **Purpose:** Generates consensus sequences from VCF/BCF files and a reference genome.
- **Main Files:**
  - `main.nf`: Nextflow process for consensus generation.
  - `environment.yml`: Conda environment for BCFtools consensus.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** VCF/BCF files, reference genome.
- **Outputs:** Consensus FASTA files.

## index
- **Purpose:** Indexes VCF/BCF files for rapid access.
- **Main Files:**
  - `main.nf`: Nextflow process for indexing.
  - `meta.yml`: Module metadata.
- **Inputs:** VCF/BCF files.
- **Outputs:** Index files (.csi/.tbi).

## mpileup
- **Purpose:** Generates pileup summaries from BAM files for variant calling.
- **Main Files:**
  - `main.nf`: Nextflow process for mpileup.
  - `environment.yml`: Conda environment for BCFtools mpileup.
  - `meta.yml`: Module metadata.
  - `tests/`: Test files for module validation.
- **Inputs:** BAM files, reference genome.
- **Outputs:** Pileup files (VCF/BCF).

## stats
- **Purpose:** Computes statistics on VCF/BCF files.
- **Main Files:**
  - `main.nf`: Nextflow process for stats.
  - `meta.yml`: Module metadata.
- **Inputs:** VCF/BCF files.
- **Outputs:** Statistics reports.

---

## Container/Conda Environment
- Each submodule defines its own environment (see `environment.yml` where present).

## Use of bin Scripts
- Modules call BCFtools commands directly; no custom bin scripts.

## Script Section Explanation
- Each module runs the appropriate BCFtools command for its function (e.g., `bcftools consensus`, `bcftools index`, `bcftools mpileup`, `bcftools stats`).

---

# Example Commands
```
bcftools consensus -f <ref.fa> <input.vcf> -o <output.fa>
bcftools index <input.vcf>
bcftools mpileup -Ou -f <ref.fa> <input.bam> | bcftools call -mv -Ob -o <output.bcf>
bcftools stats <input.vcf> > <output.stats>
```

See the BCFtools documentation for more details on usage and parameters.
