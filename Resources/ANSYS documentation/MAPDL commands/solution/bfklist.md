---
apdl: "BFKLIST"
method: bfklist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_body_loads.SolidBodyLoads.bfklist
generated: 2026-08-22
tags: [mapdl-command]
---

# BFKLIST

PyMAPDL: `mapdl.bfklist(kpoi='', lab='', **kwargs)`

Lists the body-force loads at keypoints.

## Parameters

**kpoi**: Keypoint at which body load is to be listed. If ALL (or blank), list for all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`

**lab**: Valid body load label. If ALL, use all appropriate labels. Load labels are listed under "Body Loads" in the input table for each element type in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). See the [[bfk|BFK]] command for labels.

## Notes

Lists the body-force loads for the specified keypoint and label. Keypoint body loads may be defined with the [[bfk|BFK]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFKLIST.html
