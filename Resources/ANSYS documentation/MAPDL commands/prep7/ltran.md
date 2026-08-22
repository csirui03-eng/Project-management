---
apdl: "LTRAN"
method: ltran
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ltran
generated: 2026-08-22
tags: [mapdl-command]
---

# LTRAN

PyMAPDL: `mapdl.ltran(kcnto='', nl1='', nl2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Transfers a pattern of lines to another coordinate system.

## Parameters

**kcnto**: Reference number of coordinate system where the pattern is to be transferred. Transfer occurs from the active coordinate system. The coordinate system type and parameters of `KCNTO` must be the same as the active system.

**nl1**, **nl2**, **ninc**: Transfer lines from pattern beginning with `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and pattern is all selected lines ( [[lsel|LSEL]] ). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Generate nodes and elements associated with the original lines, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether lines will be moved or newly defined:

- `0` - Generate additional lines.
- `1` - Move original lines to new position retaining the same keypoint numbers ( `KINC` and `NOELM` are ignored). Valid only if the old lines are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Transfers a pattern of lines (and their corresponding keypoints and mesh) from one coordinate system to another (see analogous node transfer command, [[transfer|TRANSFER]] ). The MAT, TYPE, REAL, and ESYS attributes are based upon the lines in the pattern and not upon the current settings. Coordinate systems may be translated and rotated relative to each other. Initial pattern may be generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Coordinate and slope values are interpreted in the active coordinate system and are transferred directly. Lines are generated as described in the [[lgen|LGEN]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LTRAN.html
