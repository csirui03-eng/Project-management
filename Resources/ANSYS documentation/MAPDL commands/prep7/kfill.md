---
apdl: "KFILL"
method: kfill
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kfill
generated: 2026-08-22
tags: [mapdl-command]
---

# KFILL

PyMAPDL: `mapdl.kfill(np1='', np2='', nfill='', nstrt='', ninc='', space='', **kwargs)`

Generates keypoints between two keypoints.

## Parameters

**np1**, **np2**: Beginning and ending keypoints for fill-in. `NP1` defaults to next to last keypoint specified, `NP2` defaults to last keypoint specified. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nfill**: Fill `NFILL` keypoints between `NP1` and `NP2` (defaults to \| `NP2` - `NP1` \|-1). `NFILL` must be positive.

**nstrt**: Keypoint number assigned to first filled-in keypoint (defaults to `NP1` + `NINC` ).

**ninc**: Add this increment to each of the remaining filled-in keypoint numbers (may be positive or negative). Defaults to ( `NP2` - `NP1` )/( `NFILL` + 1), that is, linear interpolation.

**space**: Spacing ratio. Ratio of last division size to first division size. If \> 1.0, divisions increase. If \< 1.0, divisions decrease. Ratio defaults to 1.0 (uniform spacing).

## Notes

Generates keypoints (in the active coordinate system) between two existing keypoints. The two keypoints may have been defined in any coordinate system. However, solid modeling in a toroidal coordinate system is not recommended. Any number of keypoints may be filled in and any keypoint numbering sequence may be assigned.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KFILL.html
