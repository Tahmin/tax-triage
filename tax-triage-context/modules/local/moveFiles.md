# MOVE_FILES Module

## Big Picture
The `MOVE_FILES` module renames files matching a pattern (e.g., unclassified files) to include a specified prefix or pattern, standardizing file naming for downstream analysis.

## Process Name
`MOVE_FILES`

## Container/Conda Environment
- **Conda:** `conda-forge::python=3.8.3` (if enabled)
- **Container:**
  - Singularity: `https://depot.galaxyproject.org/singularity/gawk:4.2.0`
  - Docker: `biocontainers/gawk:4.2.0`

## Inputs
- `tuple val(meta), path(files)`: Metadata and files to be renamed.
- `val(pattern)`: Pattern or prefix to add to filenames.
- `val(append_id)`: Flag to append sample ID (not used in script).
- `val(replaces)`: Replacement string (not used in script).

## Outputs
- `tuple val(meta), path("*")` (emit: files): Renamed files (optional).

## Use of bin Scripts
- Uses shell commands to rename files; no custom bin script.

## Script Section Explanation
- Iterates over files matching `*unclassified*` and renames them to include the specified pattern.

---

# Example Command
```
for f in $(ls *unclassified*); do mv "$f" "<pattern>$f"; done
```
