---
apdl: "BFLIST"
method: bflist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bflist
generated: 2026-08-22
tags: [mapdl-command]
---

# BFLIST

PyMAPDL: `mapdl.bflist(node='', lab='', **kwargs)`

Lists the body-force loads on nodes.

## Parameters

**node**: Node at which body load is to be listed. If ALL (or blank), list for all selected nodes ( [[nsel|NSEL]] ). If `Node` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). You can substitute a component name for `Node`.

**lab**: Valid body load label. If ALL (or blank), use all appropriate labels. (See [[bf|BF]].)

## Notes

Lists the body-force loads for the specified node and label. Nodal body loads are defined via [[bf|BF]].

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFLIST.html
