---
apdl: "BFDELE"
method: bfdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfdele
generated: 2026-08-22
tags: [mapdl-command]
---

# BFDELE

PyMAPDL: `mapdl.bfdele(node='', lab='', **kwargs)`

Deletes nodal body-force loads.

## Parameters

**node**: Node at which body load is to be deleted. If ALL, delete for all selected nodes ( [[nsel|NSEL]] ). If `Node` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). You can substitute a component name for `Node`.

**lab**: Valid body load label. If ALL, use all appropriate labels. See [[bf|BF]].

## Notes

Deletes nodal body-force loads for a specified node and label. Nodal body loads are defined via [[bf|BF]].

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFDELE.html
