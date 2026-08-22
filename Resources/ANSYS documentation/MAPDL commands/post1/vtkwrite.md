---
apdl: "VTKWRITE"
method: vtkwrite
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.vtkwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# VTKWRITE

PyMAPDL: `mapdl.vtkwrite(fname='', item='', **kwargs)`

Writes the current displacement data to a `.VTK` file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. Default: `Jobname`.

**item**: The output item (U, S, EPEL, or EPPL) to write to the file. Default: U.

## Notes

Writes the requested data currently in memory ( [[set|SET]] ) to a `.VTK` file that can be read by any VTK-compatible viewer (such as ParaView).

Only data associated with the currently selected element set is written.

Support is available for the displacements of 8-node brick elements (such as `SOLID185` ) only. If your model uses multiple element types, select only the 8-node elements before issuing **VTKWRITE**.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VTKWRITE.html
