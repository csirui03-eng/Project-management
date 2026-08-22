---
apdl: "ARSCALE"
method: arscale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.arscale
generated: 2026-08-22
tags: [mapdl-command]
---

# ARSCALE

PyMAPDL: `mapdl.arscale(na1='', na2='', ninc='', rx='', ry='', rz='', kinc='', noelem='', imove='', **kwargs)`

Generates a scaled set of areas from a pattern of areas.

## Parameters

**na1**, **na2**, **ninc**: Set of areas, `NA1` to `NA2` in steps of `NINC`, that defines the pattern to be scaled. `NA2` defaults to `NA1`, `NINC` defaults to 1. If `NA1` = ALL, `NA2` and `NINC` are ignored and the pattern is defined by all selected areas. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**rx**, **ry**, **rz**: Scale factors to be applied to the X, Y, and Z keypoint coordinates in the active coordinate system. ( RR, R θ, RZ for cylindrical; RR, R θ, R Φ for spherical). Note that the R θ and R Φ scale factors are interpreted as angular offsets. For example, if CSYS = 1, `RX, RY, RZ` input of (1.5,10,3) would scale the specified keypoints 1.5 times in the radial and 3 times in the Z direction, while adding an offset of 10 degrees to the keypoints. Zero, blank, or negative scale factor values are assumed to be 1.0. Zero or blank angular offsets have no effect.

**kinc**: Increment to be applied to keypoint numbers for generated set. If zero, the lowest available keypoint numbers will be assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Nodes and elements associated with the original areas will be generated (scaled) if they exist.
- `1` - Nodes and elements will not be generated.

**imove**

Specifies whether areas will be moved or newly defined:

- `0` - Additional areas will be generated.
- `1` - Original areas will be moved to new position ( `KINC` and `NOELEM` are ignored). Use only if the old areas are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates a scaled set of areas (and their corresponding keypoints, lines, and mesh) from a pattern of areas. The MAT, TYPE, REAL, and ESYS attributes are based on the areas in the pattern and not the current settings. Scaling is done in the active coordinate system. Areas in the pattern could have been generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ARSCALE.html
