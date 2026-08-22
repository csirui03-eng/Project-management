---
apdl: "VTRAN"
method: vtran
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vtran
generated: 2026-08-22
tags: [mapdl-command]
---

# VTRAN

PyMAPDL: `mapdl.vtran(kcnto='', nv1='', nv2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Transfers a pattern of volumes to another coordinate system.

## Parameters

**kcnto**: Reference number of coordinate system where the pattern is to be transferred. Transfer occurs from the active coordinate system. The coordinate system type and parameters of `KCNTO` must be the same as the active system.

**nv1**, **nv2**, **ninc**: Transfer volumes from pattern beginning with `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL, `NV2` and `NINC` are ignored and the pattern is all selected volumes ( [[vsel|VSEL]] ). If `NV1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NV1` ( `NV2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether elements and nodes are also to be generated:

- `0` - Generate nodes and elements associated with the original volumes, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether to redefine the existing volumes:

- `0` - Generate additional volumes.
- `1` - Move original volumes to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Corresponding meshed items are also moved if not needed at their original position.

## Notes

Transfers a pattern of volumes (and their corresponding keypoints, lines, areas and mesh) from one coordinate system to another (see analogous node transfer command, [[transfer|TRANSFER]] ). The MAT, TYPE, REAL, and ESYS attributes are based upon the volumes in the pattern and not upon the current settings. Coordinate systems may be translated and rotated relative to each other. Initial pattern may be generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Coordinate and slope values are interpreted in the active coordinate system and are transferred directly. Volumes are generated as described in the [[vgen|VGEN]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VTRAN.html
