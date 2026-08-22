---
apdl: "LGEN"
method: lgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lgen
generated: 2026-08-22
tags: [mapdl-command]
---

# LGEN

PyMAPDL: `mapdl.lgen(itime='', nl1='', nl2='', ninc='', dx='', dy='', dz='', kinc='', noelem='', imove='', **kwargs)`

Generates additional lines from a pattern of lines.

## Parameters

**itime**: Do this generation operation a total of `ITIME` s, incrementing all keypoints in the given pattern automatically (or by `KINC` ) each time after the first. `ITIME` must be \> 1 for generation to occur.

**nl1**, **nl2**, **ninc**: Generate lines from pattern beginning with `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and pattern is all selected lines ( [[lsel|LSEL]] ). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

**dx**, **dy**, **dz**: Keypoint location increments in the active coordinate system (-, Dθ, DZ for cylindrical, -, Dθ, - for spherical).

**kinc**: Keypoint increment between generated sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies if elements and nodes are also to be generated:

- `0` - Generate nodes and elements associated with the original lines, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether to redefine the existing lines:

- `0` - Generate additional lines as requested with the `ITIME` argument.
- `1` - Move original lines to new position retaining the same keypoint numbers ( `ITIME`, `KINC`, and `NOELM` are ignored). Valid only if the old lines are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates additional lines (and their corresponding keypoints and mesh) from a given line pattern. The MAT, TYPE, REAL, and ESYS attributes are based upon the lines in the pattern and not upon the current settings. End slopes of the generated lines remain the same (in the active coordinate system) as those of the given pattern. For example, radial slopes remain radial, etc. Generations which produce lines of a size or shape different from the pattern (that is, radial generations in cylindrical systems, radial and phi generations in spherical systems, and theta generations in elliptical systems) are not allowed. Note that solid modeling in a toroidal coordinate system is not recommended. New line numbers are automatically assigned (beginning with the lowest available values ( [[numstr|NUMSTR]] )).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LGEN.html
