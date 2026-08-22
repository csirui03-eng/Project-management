---
apdl: "KGEN"
method: kgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kgen
generated: 2026-08-22
tags: [mapdl-command]
---

# KGEN

PyMAPDL: `mapdl.kgen(itime='', np1='', np2='', ninc='', dx='', dy='', dz='', kinc='', noelem='', imove='', **kwargs)`

Generates additional keypoints from a pattern of keypoints.

## Parameters

**itime**: Do this generation operation a total of `ITIME` times, incrementing all keypoints in the given pattern automatically (or by `KINC` ) each time after the first. `ITIME` must be more than 1 for generation to occur.

**np1**, **np2**, **ninc**: Generate keypoints from the pattern of keypoints beginning with `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and the pattern is all selected keypoints ( [[ksel|KSEL]] ). If `NP1` is negative, `NP2` and `NINC` are ignored and the last \| `NP1` \| keypoints (in sequence from the highest keypoint number) are used as the pattern to be repeated. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

**dx**, **dy**, **dz**: Keypoint location increments in the active coordinate system (DR, Dθ, DZ for cylindrical, DR, Dθ, DΦ for spherical).

**kinc**: Keypoint increment between generated sets. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

**noelem**

Specifies if elements and nodes are also to be generated:

- `0` - Generate nodes and point elements associated with the original keypoints, if they exist.
- `1` - Do not generate nodes and elements.

**imove**

Specifies whether keypoints will be moved or newly defined:

- `0` - Generate additional keypoints as requested with the `ITIME` argument.
- `1` - Move original keypoints to new position retaining the same keypoint numbers ( `ITIME`, `KINC`, and `NOELEM` are ignored). Valid only if the old keypoints are no longer needed at their original positions. Corresponding meshed items are also moved if not needed at their original position.

## Notes

Generates additional keypoints (and corresponding mesh) from a given keypoint pattern. The MAT, TYPE, REAL, and ESYS attributes are based upon the keypoints in the pattern and not upon the current settings. Generation is done in the active coordinate system. Keypoints in the pattern may have been defined in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KGEN.html
