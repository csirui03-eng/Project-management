---
apdl: "NMODIF"
method: nmodif
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nmodif
generated: 2026-08-22
tags: [mapdl-command]
---

# NMODIF

PyMAPDL: `mapdl.nmodif(node='', x='', y='', z='', thxy='', thyz='', thzx='', **kwargs)`

Modifies an existing node.

## Parameters

**node**: Modify coordinates of this node. If ALL, modify coordinates of all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**x**, **y**, **z**: Replace the previous coordinate values assigned to this node with these corresponding coordinate values. Values are interpreted in the active coordinate system (R, θ, Z for cylindrical; R, θ, Φ for spherical or toroidal). Leaving any of these fields blank retains the previous value(s).

**thxy**: First rotation of nodal coordinate system about nodal Z (positive X toward Y). Leaving this field blank retains the previous value.

**thyz**: Second rotation of nodal coordinate system about nodal X (positive Y toward Z). Leaving this field blank retains the previous value.

**thzx**: Third rotation of nodal coordinate system about nodal Y (positive Z toward X). Leaving this field blank retains the previous value.

## Notes

Modifies an existing node. Nodal coordinate system rotation angles are in degrees and redefine any existing rotation angles. Nodes can also be redefined with the [[n|N]] command.

See the [[nrotat|NROTAT]], [[nang|NANG]], and [[nora|NORA]] commands for other rotation options.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NMODIF.html
