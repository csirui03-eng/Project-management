---
apdl: "MAT"
method: mat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mat
generated: 2026-08-22
tags: [mapdl-command]
---

# MAT

PyMAPDL: `mapdl.mat(mat='', **kwargs)`

Sets the element material attribute pointer.

## Parameters

**mat**: Assign this material number to subsequently defined elements (defaults to 1).

## Notes

Identifies the material number to be assigned to subsequently defined elements. This number refers to the material number ( `MAT` ) defined with the material properties ( [[mp|MP]] ). Material numbers may be displayed ( [[pnum|/PNUM]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MAT.html
