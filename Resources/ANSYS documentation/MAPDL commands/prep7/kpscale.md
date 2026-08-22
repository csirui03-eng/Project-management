---
apdl: "KPSCALE"
method: kpscale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kpscale
generated: 2026-08-22
tags: [mapdl-command]
---

# KPSCALE

PyMAPDL: `mapdl.kpscale(np1='', np2='', ninc='', rx='', ry='', rz='', kinc='', noelem='', imove='', **kwargs)`

Generates a scaled set of (meshed) keypoints from a pattern of keypoints.

## Parameters

**np1**, **np2**, **ninc**: Set of keypoints ( `NP1` to `NP2` in steps of `NINC` ) that defines the pattern to be scaled. `NP2` defaults to `NP1`, `NINC` defaults to 1. If `NP1` = ALL, `NP2` and `NINC` are ignored and the pattern is defined by all selected keypoints. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

**rx**, **ry**, **rz**: Scale factors to be applied to the X, Y, Z keypoint coordinates in the active coordinate system (RR, Rθ, RZ for cylindrical; RR, Rθ, RΦ for spherical). The Rθ and RΦ scale factors are interpreted as angular offsets. For example, if CSYS = 1, an `RX`, `RY`, `RZ` input of (1.5,10,3) would scale the specified keypoints 1.5 times in the radial and 3 times in the Z direction, while adding an offset of 10 degrees to the keypoints.) Zero, blank, or negative scale factor values are assumed to be 1.0. Zero or blank angular offsets have no effect.

**kinc**: Increment to be applied to the keypoint numbers for generated set. If zero, the lowest available keypoint numbers will be assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies whether nodes and elements are also to be generated:

- `0` - Nodes and point elements associated with the original keypoints will be generated (scaled) if they exist.
- `1` - Nodes and point elements will not be generated.

**imove**

Specifies whether keypoints will be moved or newly defined:

- `0` - Additional keypoints will be generated.
- `1` - Original keypoints will be moved to new position ( `KINC` and `NOELEM` are ignored). Use only if the old keypoints are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates a scaled set of keypoints (and corresponding mesh) from a pattern of keypoints. The MAT, TYPE, REAL, and ESYS attributes are based on the keypoints in the pattern and not the current settings. Scaling is done in the active coordinate system. Keypoints in the pattern could have been generated in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KPSCALE.html
