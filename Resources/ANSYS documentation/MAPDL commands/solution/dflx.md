---
apdl: "DFLX"
method: dflx
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dflx
generated: 2026-08-22
tags: [mapdl-command]
---

# DFLX

PyMAPDL: `mapdl.dflx(node='', bx='', by='', bz='', bx2='', by2='', bz2='', **kwargs)`

Imposes a uniform magnetic flux B on an edge-element electromagnetic model.

## Parameters

**node**: Nodes at which the edge-flux (AZ) constraints corresponding to the uniform magnetic flux are to be specified. Valid options are ALL (default) or Component Name. If ALL, constraints are applied to all selected nodes ( [[nsel|NSEL]] ).

**bx**, **by**, **bz**: Real components of magnetic flux B.

**bx2**, **by2**, **bz2**: Imaginary components of magnetic flux B.

## Notes

The **DFLX** command sets the constraints on the edge-flux (AZ) degrees of freedom to produce a uniform magnetic flux B in an edge-based electromagnetic analysis using one of these element types: `SOLID226`, `SOLID227`, `SOLID236`, or `SOLID237`. The command ignores the corner nodes of the elements (even if they were selected) and imposes the AZ-constraints on the mid-side nodes only. The AZ-constraints are imposed in the active Cartesian coordinate system. A non-Cartesian coordinate system will be ignored by the **DFLX** command.

The edge-flux constraints at the mid-side nodes are derived from the magnetic vector potential **A**, which is related to the imposed magnetic flux **B** as follows:

(equation not available in the PyMAPDL source, see the Ansys help page)

where **r** is the position of the mid-side node.

The **DFLX** command creates a component named DFLX for the constrained midside nodes. You can use this component to delete the constraints imposed by the **DFLX** command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DFLX.html
