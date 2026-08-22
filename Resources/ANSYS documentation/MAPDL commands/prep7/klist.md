---
apdl: "KLIST"
method: klist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.klist
generated: 2026-08-22
tags: [mapdl-command]
---

# KLIST

PyMAPDL: `mapdl.klist(np1='', np2='', ninc='', lab='', **kwargs)`

Lists the defined keypoints or hard points.

## Parameters

**np1**, **np2**, **ninc**: List keypoints from `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL (default), `NP2` and `NINC` are ignored and all selected keypoints ( [[ksel|KSEL]] ) are listed. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

**lab**

Coordinate listing key:

- `(blank)` - List all keypoint information.
- `COORD` - Suppress all but the keypoint coordinates (shown to a higher degree of accuracy than when displayed with all information).
- `HPT` - List only hard point information.

## Notes

Lists keypoints in the active display coordinate system ( [[dsys|DSYS]] ). An attribute (TYPE, MAT, REAL, or ESYS) listed as a zero is unassigned; one listed as a positive value indicates that the attribute was assigned with the [[katt|KATT]] command (and will not be reset to zero if the mesh is cleared); one listed as a negative value indicates that the attribute was assigned using the attribute pointer ( [[type|TYPE]], [[mat|MAT]], [[real|REAL]], or [[esys|ESYS]] ) that was active during meshing (and will be reset to zero if the mesh is cleared).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KLIST.html
