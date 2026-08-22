---
apdl: "VOVLAP"
method: vovlap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.vovlap
generated: 2026-08-22
tags: [mapdl-command]
---

# VOVLAP

PyMAPDL: `mapdl.vovlap(nv1='', nv2='', nv3='', nv4='', nv5='', nv6='', nv7='', nv8='', nv9='', **kwargs)`

Overlaps volumes.

## Parameters

**nv1**, **nv2**, **nv3**, **nv4**, **nv5**, **nv6**, **nv7**, **nv8**, **nv9**: Numbers of volumes to be operated on. If `NV1` = ALL, `NV2` to `NV9` are ignored and all selected volumes are used. If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1`.

## Notes

Overlaps volumes. Generates new volumes which encompass the geometry of all the input volumes. The new volumes are defined by the regions of intersection of the input volumes, and by the complementary (non-intersecting) regions. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. This operation is only valid when the region of intersection is a volume. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VOVLAP.html
