---
apdl: "KTRAN"
method: ktran
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.ktran
generated: 2026-08-22
tags: [mapdl-command]
---

# KTRAN

PyMAPDL: `mapdl.ktran(kcnto='', np1='', np2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Transfers a pattern of keypoints to another coordinate system.

## Parameters

**kcnto**: Reference number of coordinate system where the pattern is to be transferred. Transfer occurs from the active coordinate system.

**np1**, **np2**, **ninc**: Transfer keypoints from pattern beginning with `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and pattern is all selected keypoints ( [[ksel|KSEL]] ). If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Generate nodes and point elements associated with the original keypoints, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether keypoints will be moved or newly defined:

- `0` - Generate additional keypoints.
- `1` - Move original keypoints to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Valid only if the old keypoints are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Transfers a pattern of keypoints (and corresponding mesh) from one coordinate system to another (see analogous node transfer command, [[transfer|TRANSFER]] ). The MAT, TYPE, REAL, and ESYS attributes are based upon the keypoints in the pattern and not upon the current settings. Coordinate systems may be translated and rotated relative to each other. Initial pattern may be generated in any coordinate system. Coordinate values are interpreted in the active coordinate system and are transferred directly. Solid modeling in a toroidal coordinate system is not recommended.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KTRAN.html
