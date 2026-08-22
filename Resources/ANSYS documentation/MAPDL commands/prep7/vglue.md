---
apdl: "VGLUE"
method: vglue
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vglue
generated: 2026-08-22
tags: [mapdl-command]
---

# VGLUE

PyMAPDL: `mapdl.vglue(nv1='', nv2='', nv3='', nv4='', nv5='', nv6='', nv7='', nv8='', nv9='', **kwargs)`

Generates new volumes by "gluing" volumes.

## Parameters

**nv1**, **nv2**, **nv3**, **nv4**, **nv5**, **nv6**, **nv7**, **nv8**, **nv9**: Numbers of the volumes to be glued. If `NV1` = ALL, all selected volumes will be glued ( `NV2` to `NV9` will be ignored). If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1`.

## Notes

Use of the **VGLUE** command generates new volumes by gluing input volumes. The glue operation redefines the input volumes so that they share areas along their common boundaries. The new volumes encompass the same geometry as the original volumes. This operation is only valid if the intersections of the input volumes are areas along the boundaries of those volumes. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

The **VGLUE** command results in the merging of areas, lines, and keypoints at the common volume boundaries. The areas, lines, and keypoints of the lower numbered volume will be kept. This means one must be aware of volume numbering when multiple **VGLUE** commands are applied to avoid any ungluing of geometry.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VGLUE.html
