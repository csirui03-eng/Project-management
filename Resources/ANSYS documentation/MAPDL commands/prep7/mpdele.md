---
apdl: "MPDELE"
method: mpdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpdele
generated: 2026-08-22
tags: [mapdl-command]
---

# MPDELE

PyMAPDL: `mapdl.mpdele(lab='', mat1='', mat2='', inc='', lchk='', **kwargs)`

Deletes linear material properties.

## Parameters

**lab**: Material property label (see [[mp|MP]] command for valid labels). If ALL, delete properties for all applicable labels.

**mat1**, **mat2**, **inc**: Delete materials from `MAT1` to `MAT2` (defaults to `MAT1` ) in steps of `INC` (defaults to 1). If `MAT1` = ALL, `MAT2` and `INC` are ignored and the properties for all materials are deleted.

**lchk**

Specifies the level of element-associativity checking:

- `NOCHECK` - No element-associativity check occurs. This option is the default.
- `WARN` - When a section, material, or real constant is associated with an element, Mechanical APDL issues a message warning that the necessary entity has been deleted.
- `CHECK` - The command terminates, and no section, material, or real constant is deleted if it is associated with an element.

## Notes

This command is also valid in SOLUTION.

The `LCHK` argument is valid only when `Lab` = ALL.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPDELE.html
