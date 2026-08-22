---
apdl: "WRITE"
method: write
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiation_matrix_method.RadiationMatrixMethod.write
generated: 2026-08-22
tags: [mapdl-command]
---

# WRITE

PyMAPDL: `mapdl.write(fname='', **kwargs)`

Writes the radiation matrix file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name Defaults to `Jobname`.

## Notes

Writes radiation matrix file ( `File.SUB` ) for input to the substructure thermal "use" pass. Subsequent **WRITE** operations to the same file overwrite the file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WRITE.html
