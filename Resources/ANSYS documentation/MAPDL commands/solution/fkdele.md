---
apdl: "FKDELE"
method: fkdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_forces.SolidForces.fkdele
generated: 2026-08-22
tags: [mapdl-command]
---

# FKDELE

PyMAPDL: `mapdl.fkdele(kpoi='', lab='', **kwargs)`

Deletes force loads at a keypoint.

## Parameters

**kpoi**: Keypoint at which force is to be deleted. If ALL, delete forces at all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

**lab**: Valid force label. If ALL, use all appropriate labels. See the [[fdele|FDELE]] command for labels.

## Notes

Deletes force loads (and all corresponding finite element loads) at a keypoint. See the [[fdele|FDELE]] command for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FKDELE.html
