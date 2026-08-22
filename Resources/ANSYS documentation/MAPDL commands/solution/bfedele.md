---
apdl: "BFEDELE"
method: bfedele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfedele
generated: 2026-08-22
tags: [mapdl-command]
---

# BFEDELE

PyMAPDL: `mapdl.bfedele(elem='', lab='', **kwargs)`

Deletes element body-force loads.

## Parameters

**elem**: Element at which body load is to be deleted. If ALL, delete for all selected elements \[ A component name may also be substituted for `ELEM`.

**lab**: Valid body load label. If ALL, use all appropriate labels. See [[bfe|BFE]] command for labels.

## Notes

Deletes element body-force loads for a specified element and label. Element body loads may be defined with the [[bfe|BFE]] commands.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFEDELE.html
