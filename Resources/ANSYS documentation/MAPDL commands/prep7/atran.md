---
apdl: "ATRAN"
method: atran
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.atran
generated: 2026-08-22
tags: [mapdl-command]
---

# ATRAN

PyMAPDL: `mapdl.atran(kcnto='', na1='', na2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Transfers a pattern of areas to another coordinate system.

## Parameters

**kcnto**: Reference number of coordinate system where the pattern is to be transferred. Transfer occurs from the active coordinate system. The coordinate system type and parameters of `KCNTO` must be the same as the active system.

**na1**, **na2**, **ninc**: Transfer area pattern beginning with `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL, `NA2` and `NINC` are ignored and the pattern is all selected areas ( [[asel|ASEL]] ). If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether elements and nodes are also to be generated:

- `0` - Generate nodes and elements associated with the original areas, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether to redefine the existing areas:

- `0` - Generate additional areas.
- `1` - Move original areas to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Valid only if the old areas are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Transfers a pattern of areas (and their corresponding lines, keypoints and mesh) from one coordinate system to another (see analogous node [[transfer|TRANSFER]] command). The MAT, TYPE, REAL, and ESYS attributes are based upon the areas in the pattern and not upon the current settings. Coordinate systems may be translated and rotated relative to each other. Initial pattern may be generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Coordinate and slope values are interpreted in the active coordinate system and are transferred directly. Areas are generated as described in the [[agen|AGEN]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ATRAN.html
