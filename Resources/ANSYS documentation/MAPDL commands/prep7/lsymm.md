---
apdl: "LSYMM"
method: lsymm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lsymm
generated: 2026-08-22
tags: [mapdl-command]
---

# LSYMM

PyMAPDL: `mapdl.lsymm(ncomp='', nl1='', nl2='', ninc='', kinc='', noelem='', imove='', **kwargs)`

Generates lines from a line pattern by symmetry reflection.

## Parameters

**ncomp**

Symmetry key:

- `X` - X symmetry (default).
- `Y` - Y symmetry.
- `Z` - Z symmetry.

**nl1**, **nl2**, **ninc**: Reflect lines from pattern beginning with `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and pattern is all selected lines ( [[lsel|LSEL]] ). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

**kinc**: Keypoint increment between sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Generate nodes and elements associated with the original lines, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether areas will be moved or newly defined:

- `0` - Generate additional lines.
- `1` - Move original lines to new position retaining the same keypoint numbers ( `KINC` and `NOELEM` are ignored). Valid only if the old lines are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates a reflected set of lines (and their corresponding keypoints and mesh) from a given line pattern by a symmetry reflection (see analogous node symmetry command, [[nsym|NSYM]] ). The MAT, TYPE, REAL, and ESYS attributes are based upon the lines in the pattern and not upon the current settings. Reflection is done in the active coordinate system by changing a particular coordinate sign. The active coordinate system must be Cartesian. Lines in the pattern may have been generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Lines are generated as described in the [[lgen|LGEN]] command.

See the [[esym|ESYM]] command for additional information about symmetry elements.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSYMM.html
