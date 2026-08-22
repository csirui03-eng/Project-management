---
apdl: "MPLIST"
method: mplist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mplist
generated: 2026-08-22
tags: [mapdl-command]
---

# MPLIST

PyMAPDL: `mapdl.mplist(mat1='', mat2='', inc='', lab='', tevl='', **kwargs)`

Lists linear material properties.

## Parameters

**mat1**, **mat2**, **inc**: List materials from `MAT1` to `MAT2` (defaults to `MAT1` ) in steps of `INC` (defaults to 1). If `MAT1` = ALL (default), `MAT2` and `INC` are ignored and properties for all material numbers are listed.

**lab**: Material property label (see the [[mp|MP]] command for labels). If ALL (or blank), list properties for all labels. If EVLT, list properties for all labels evaluated at TEVL.

**tevl**: Evaluation temperature for `Lab` = EVLT listing (defaults to [[bfunif|BFUNIF]] ).

## Notes

For `Lab` = EVLT, when the property is from tables, the [[mpplot|MPPLOT]] command will not be valid because the property could be a function of more than temperature.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPLIST.html
