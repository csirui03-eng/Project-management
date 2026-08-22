---
apdl: "AREVERSE"
method: areverse
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.areverse
generated: 2026-08-22
tags: [mapdl-command]
---

# AREVERSE

PyMAPDL: `mapdl.areverse(anum='', noeflip='', **kwargs)`

Reverses the normal of an area, regardless of its connectivity or mesh status.

## Parameters

**anum**: Area number of the area whose normal is to be reversed. If `ANUM` = ALL, the normals of all selected areas will be reversed. If `ANUM` = P, graphical picking is enabled. A component name may also be substituted for `ANUM`.

**noeflip**

Indicates whether you want to change the normal direction of the existing elements on the reversed area(s) so that they are consistent with each area's new normal direction.

- `0` - Make the normal direction of existing elements on the reversed area(s) consistent with each area's new normal direction (default).
- `1` - Do not change the normal direction of existing elements on the reversed area(s).

## Notes

You cannot use the **AREVERSE** command to change the normal direction of any element that has a body or surface load. We recommend that you apply all of your loads only after ensuring that the element normal directions are acceptable. Also, you cannot use this command to change the normal direction for areas attached to volumes because IGES and ANF data is unchanged by reversal. Reversed areas that are attached to volumes need to be reversed again when imported.

Real constants (such as nonuniform shell thickness and tapered beam constants) may be invalidated by an element reversal.

See [Revising Your Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD8_6.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AREVERSE.html
