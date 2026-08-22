---
apdl: "KDELE"
method: kdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kdele
generated: 2026-08-22
tags: [mapdl-command]
---

# KDELE

PyMAPDL: `mapdl.kdele(np1='', np2='', ninc='', **kwargs)`

Deletes unmeshed keypoints.

## Parameters

**np1**, **np2**, **ninc**: Delete keypoints from `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and all selected keypoints ( [[ksel|KSEL]] ) are deleted. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1` ( `NP2` and `NINC` are ignored).

## Notes

Deletes selected keypoints. A keypoint attached to a line cannot be deleted unless the line is first deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KDELE.html
