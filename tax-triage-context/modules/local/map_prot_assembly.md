# MAP_PROT_ASSEMBLY Module

## Big Picture
The `MAP_PROT_ASSEMBLY` module maps protein features from DIAMOND output to assemblies, producing a protein-to-assembly mapping file for downstream analysis.

## Process Name
`MAP_PROT_ASSEMBLY`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3 pysam` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/pysam:0.21.0--py39hcada746_1`
  - Docker: `biocontainers/pysam:0.21.0--py39hcada746_1`

## Inputs
- `tuple val(meta), file(diamondoutput), file(features), file(mapping), file(map_names)`: Metadata and input files for mapping.
- `file(assembly)`: Reference assembly file.

## Outputs
- `tuple val(meta), path("*assembly_protein_map.txt")` (emit: promap): Protein-to-assembly mapping file.

## Use of bin Scripts
- Uses `map_prot_assembly.py` from the pipeline's `bin/` directory to perform the mapping.

## Script Section Explanation
- Runs `map_prot_assembly.py` with DIAMOND output, features, assembly, mapping, and optional map names.
- Captures Python version information in `versions.yml`.

---

# Example Command
```
map_prot_assembly.py -d <diamondoutput> -f <features> -a <assembly> -n <mapping> [--mapnames <map_names>] -o <output.txt>
```
