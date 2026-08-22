---
apdl: "TYPE"
method: type
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.type
generated: 2026-08-22
tags: [mapdl-command]
---

# TYPE

PyMAPDL: `mapdl.type(itype='', **kwargs)`

Sets the element type attribute pointer.

## Parameters

**itype**: Assign a type number to the elements (defaults to 1).

## Notes

Assigns an element-type number to subsequently defined elements. The number refers to the element- type number ( `ITYPE` ) defined with via [[et|ET]]. You can display type numbers ( [[pnum|/PNUM]] ).

In some cases, the program can proceed with a meshing operation even when no logical element type has been assigned via **TYPE** or **XATT**, `TYPE`. For more information, see the discussion for setting element attributes in [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TYPE.html
