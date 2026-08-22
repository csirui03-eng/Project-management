---
apdl: "BFKDELE"
method: bfkdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bfkdele
generated: 2026-08-22
tags: [mapdl-command]
---

# BFKDELE

PyMAPDL: `mapdl.bfkdele(kpoi='', lab='', **kwargs)`

Deletes body-force loads at a keypoint.

## Parameters

**kpoi**: Keypoint at which body load is to be deleted. If ALL, delete for all selected keypoints ( [[ksel|KSEL]] ). A component name may also be substituted for `KPOI`.

**lab**: Valid body load label. If ALL, use all appropriate labels. Load labels are listed under "Body Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). See the [[bfk|BFK]] command for labels.

## Notes

Deletes body-force loads (and all corresponding finite element loads) for a specified keypoint and label. Body loads may be defined at a keypoint with the [[bfk|BFK]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFKDELE.html
