---
apdl: "NKPT"
method: nkpt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nkpt
generated: 2026-08-22
tags: [mapdl-command]
---

# NKPT

PyMAPDL: `mapdl.nkpt(node='', npt='', **kwargs)`

Defines a node at an existing keypoint location.

## Parameters

**node**: Arbitrary reference number for node. If zero or blank, defaults to the highest node number +1 ( [[numstr|NUMSTR]] ).

**npt**: Keypoint number defining global X, Y, Z location. If `NPT` = All, then a node will be placed at each selected keypoint. If `NPT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NPT`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NKPT.html
