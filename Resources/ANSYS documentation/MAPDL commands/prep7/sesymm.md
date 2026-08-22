---
apdl: "SESYMM"
method: sesymm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.superelements.Superelements.sesymm
generated: 2026-08-22
tags: [mapdl-command]
---

# SESYMM

PyMAPDL: `mapdl.sesymm(sename='', ncomp='', inc='', file='', ext='', **kwargs)`

Performs a symmetry operation on a superelement within the use pass.

## Parameters

**sename**: The name (case-sensitive) of the superelement matrix file created by the substructure generation pass ( `Sename.SUB` ). Defaults to the current `Jobname`. If a number, it is the element number of a previously defined superelement in the current use pass.

**ncomp**

Symmetry key:

- `X` - X symmetry (default).
- `Y` - Y symmetry.
- `Z` - Z symmetry.

**inc**: Increment all nodes in the superelement by `INC`.

**file**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. This field must be input.

**ext**: Filename extension (eight-character maximum). The extension defaults to SUB.

## Notes

Performs a symmetry operation on a superelement within the substructure use pass by reversing the sign of component `Ncomp` in the global Cartesian coordinate system. The node numbers are incremented by `INC`. The new superelement is written to `File.SUB` in the current directory (by default). All master node nodal coordinate systems must be global Cartesian (no rotated nodes allowed).

The maximum number of transformations for a given superelement is five (including [[setran|SETRAN]], **SESYMM**, and the large rotation transformation if [[nlgeom|NLGEOM]] is ON in the use pass).

This command is not supported if the original superelement matrix was created in a component mode synthesis analysis generation pass with the element results calculation activated ( `Elcalc` = YES on [[cmsopt|CMSOPT]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SESYMM.html
