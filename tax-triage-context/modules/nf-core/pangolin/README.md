# Pangolin Module

## Big Picture
The `pangolin` module runs Pangolin, a tool for assigning SARS-CoV-2 lineages from genome assemblies.

## Main Files
- `main.nf`: Nextflow process definition for Pangolin.
- `meta.yml`: Module metadata.

## Inputs
- SARS-CoV-2 genome assemblies (FASTA files).

## Outputs
- Lineage assignment reports (CSV, TXT).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a Pangolin container/environment.

## Use of bin Scripts
- Calls Pangolin directly; no custom bin script in this module.

## Script Section Explanation
- Runs Pangolin with user-specified parameters for lineage assignment.

---

# Example Command
```
pangolin <assembly.fasta> --outfile <output.csv>
```

See the Pangolin documentation for more details on usage and parameters.
