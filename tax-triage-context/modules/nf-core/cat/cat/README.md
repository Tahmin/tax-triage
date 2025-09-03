# CAT Module

## Big Picture
The `cat/cat` module runs CAT (Contig Annotation Tool), which annotates contigs with taxonomic information based on sequence similarity.

## Main Files
- `main.nf`: Nextflow process definition for CAT.
- `meta.yml`: Module metadata.

## Inputs
- Contig sequences (FASTA files).
- Reference database for annotation.

## Outputs
- Annotated contigs with taxonomic assignments (tabular or standard CAT output).

## Container/Conda Environment
- Defined in the module or inherited from the pipeline; typically uses a CAT container/environment.

## Use of bin Scripts
- Calls CAT directly; no custom bin script in this module.

## Script Section Explanation
- Runs CAT with user-specified parameters for contig annotation.

---

# Example Command
```
CAT contigs -c <contigs.fa> -d <CAT_db_dir> -t <taxonomy_folder> -o <output_dir>
```

See the CAT documentation for more details on usage and parameters.
