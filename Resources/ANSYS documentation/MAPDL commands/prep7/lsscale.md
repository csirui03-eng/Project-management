---
apdl: "LSSCALE"
method: lsscale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lsscale
generated: 2026-08-22
tags: [mapdl-command]
---

# LSSCALE

PyMAPDL: `mapdl.lsscale(nl1='', nl2='', ninc='', rx='', ry='', rz='', kinc='', noelem='', imove='', **kwargs)`

Generates a scaled set of lines from a pattern of lines.

## Parameters

**nl1**, **nl2**, **ninc**: Set of lines ( `NL1` to `NL2` in steps of `NINC` ) that defines the pattern to be scaled. `NL2` defaults to `NL1`, `NINC` defaults to 1. If `NL1` = ALL, `NL2` and `NINC` are ignored and the pattern is defined by all selected lines. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

**rx**, **ry**, **rz**: Scale factors to be applied to the X, Y, Z keypoint coordinates in active coordinate system ( RR, R θ, RZ for cylindrical; RR, R θ, R Φ for spherical). Note that the R θ and R Φ scale factors are interpreted as angular offsets. For example, for [[csys|CSYS]],1, RR, R θ, RZ input of (1.5,10,3) would scale the specified keypoints 1.5 times in the radial and 3 times in the Z direction, while adding an offset of 10 degrees to the keypoints. Zero, blank, or negative scale factor values are assumed to be 1.0. Zero or blank angular offsets have no effect.

**kinc**: Increment to be applied to keypoint numbers for generated set. If zero, the lowest available keypoint numbers will be assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Nodes and line elements associated with the original lines will be generated (scaled) if they exist.
- `1` - Nodes and line elements will not be generated.

**imove**

Specifies whether lines will be moved or newly defined:

- `0` - Additional lines will be generated.
- `1` - Original lines will be moved to new position ( `KINC` and `NOELEM` are ignored). Use only if the old lines are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

This command generates a scaled set of lines (and their corresponding keypoints and mesh) from a pattern of lines.

The MAT, TYPE, REAL, and ESYS attributes are based on the lines in the pattern and not the current settings.

Scaling occurs in the active coordinate system. Lines in the pattern could have been generated in any coordinate system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSSCALE.html
