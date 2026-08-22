---
apdl: "KCLEAR"
method: kclear
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.kclear
generated: 2026-08-22
tags: [mapdl-command]
---

# KCLEAR

PyMAPDL: `mapdl.kclear(np1='', np2='', ninc='', **kwargs)`

Deletes nodes and point elements associated with selected keypoints.

## Parameters

**np1**, **np2**, **ninc**: Delete mesh for keypoints `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and the mesh for all selected keypoints ( [[ksel|KSEL]] ) is deleted. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1`.

## Notes

Deletes all nodes and point elements associated with selected keypoints (regardless of whether the nodes or elements are selected). Nodes associated with non-point elements will not be deleted. Attributes assigned as a result of [[katt|KATT]] are maintained. In the program's response to the command, if a keypoint is tallied as cleared, it means either its node or element reference was deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KCLEAR.html
