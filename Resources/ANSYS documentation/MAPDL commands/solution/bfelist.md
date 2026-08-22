---
apdl: "BFELIST"
method: bfelist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfelist
generated: 2026-08-22
tags: [mapdl-command]
---

# BFELIST

PyMAPDL: `mapdl.bfelist(elem='', lab='', **kwargs)`

Lists the element body-force loads.

## Parameters

**elem**: Element at which body load is to be listed. If ALL (or blank), list for all selected elements ( [[esel|ESEL]] ). If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `ELEM`.

**lab**: Valid body load label. If ALL (or blank), use all appropriate labels. See [[bfe|BFE]] command for labels.

## Notes

Lists the element body-force loads for the specified element and label. Element body loads may be defined with the [[bfe|BFE]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFELIST.html
