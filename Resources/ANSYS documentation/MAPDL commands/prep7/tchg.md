---
apdl: "TCHG"
method: tchg
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.tchg
generated: 2026-08-22
tags: [mapdl-command]
---

# TCHG

PyMAPDL: `mapdl.tchg(ename1='', ename2='', etype2='', **kwargs)`

Converts 20-node degenerate tetrahedral elements to their 10-node non-degenerate counterparts.

## Parameters

**ename1**: Name (or the number) of the 20-node tetrahedron element that you want to convert. This argument is required.

**ename2**: Name (or the number) of the 10-node tetrahedron element to which you want to convert the `ENAME` elements. This argument is required.

**etype2**: Element TYPE reference number for `ENAME2`. If `ETYPE2` is 0 or is not specified, the program selects the element TYPE reference number for `ENAME2`. See the [[tchg#Notes|TCHG]] section for details. This argument is optional.

## Notes

The **TCHG** command allows you to specify conversion of any selected 20-node brick that is degenerated into a tetrahedron to a 10-node tetrahedron.

The **TCHG** command is useful when used in with the [[mopt|MOPT]],PYRA command. Twenty-node pyramid shaped elements may be used in the same volume with 10-node tetrahedra.

Performing a conversion is likely to create circumstances in which more than one element type is defined for a single volume.

If specified, `ETYPE2` will usually be the same as the local element TYPE number ( [[et|ET]], `ITYPE` ) that was assigned to `ENAME2` with the [[et|ET]] command. You can specify a unique number for `ETYPE2` if you prefer. Although `ETYPE2` is optional, it may be useful when two or more `ITYPE` s have been assigned to the same element (for example, if two `SOLID187` elements have been established in the element attribute tables for the current model, use the `ETYPE2` argument to distinguish between them). If `ETYPE2` is nonzero and it has not already been assigned to an element via [[et|ET]], the program assigns the `ETYPE2` value to `ENAME2` as its element TYPE reference number.

If `ETYPE2` is 0 or is not specified, the program determines the element TYPE reference number for `ENAME2` in one of these ways:

- If `ETYPE2` is 0 or is not specified, and `ENAME2` does not appear in the element attribute tables, the program uses the next available (unused) location in the element attribute tables to determine the element TYPE reference number for `ENAME2`.
- If `ETYPE2` is 0 or is not specified, and `ENAME2` appears in the element attribute tables, the program uses `ENAME2` 's existing element TYPE reference number for `ETYPE2`. (If there is more than one occurrence of `ENAME2` in the element attribute tables (each with its own TYPE reference number), the program uses the first `ENAME2` reference number for `ETYPE2`.)

You cannot use element conversion if boundary conditions or loads are applied directly to any selected elements.

For more information about converting degenerate tetrahedral elements, see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TCHG.html
