---
apdl: "ANORM"
method: anorm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.anorm
generated: 2026-08-22
tags: [mapdl-command]
---

# ANORM

PyMAPDL: `mapdl.anorm(anum='', noeflip='', **kwargs)`

Reorients area normals.

## Parameters

**anum**: Area number having the normal direction that the reoriented areas are to match.

**noeflip**

Indicates whether you want to change the normal direction of the existing elements on the reoriented area(s) so that they are consistent with each area's new normal direction.

- `0` - Make the normal direction of existing elements on the reoriented area(s) consistent with each area's new normal direction (default).
- `1` - Do not change the normal direction of existing elements on the reoriented area(s).

## Notes

Reorients areas so that their normals are consistent with that of a specified area.

If any of the areas have inner loops, the **ANORM** command will consider the inner loops when it reorients the area normals.

You cannot use the **ANORM** command to change the normal direction of any element that has a body or surface load. We recommend that you apply all of your loads only after ensuring that the element normal directions are acceptable.

Real constants (such as nonuniform shell thickness and tapered beam constants) may be invalidated by an element reversal.

See [Revising Your Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD8_6.html) of the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANORM.html
