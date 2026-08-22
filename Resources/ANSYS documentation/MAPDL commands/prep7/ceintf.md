---
apdl: "CEINTF"
method: ceintf
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.ceintf
generated: 2026-08-22
tags: [mapdl-command]
---

# CEINTF

PyMAPDL: `mapdl.ceintf(toler='', dof1='', dof2='', dof3='', dof4='', dof5='', dof6='', movetol='', **kwargs)`

Generates constraint equations at an interface.

## Parameters

**toler**: Tolerance about selected elements, based on a fraction of the element dimension (defaults to 0.25 (25%)). Nodes outside the element by more than the tolerance are not accepted as being on the interface.

**dof1**, **dof2**, **dof3**, **dof4**, **dof5**, **dof6**: Degrees of freedom for which constraint equations are written. Defaults to all applicable DOFs. `DOF1` accepts ALL as a valid label, in which case the rest are ignored (all DOFs are applied).

**movetol**: The allowed "motion" of a node (see Note below). This distance is in terms of the element coordinates (-1.0 to 1.0). A typical value is 0.05. Defaults to 0 (do not move). `MoveTol` must be less than or equal to `TOLER`.

## Notes

This command can be used to "tie" together two regions with dissimilar mesh patterns by generating constraint equations that connect the selected nodes of one region to the selected elements of the other region. At the interface between regions, nodes should be selected from the more dense mesh region, A, and the elements selected from the less dense mesh region, B. The degrees of freedom of region A nodes are interpolated with the corresponding degrees of freedom of the nodes on the region B elements, using the shape functions of the region B elements. Constraint equations are then written that relate region A and B nodes at the interface.

The `MoveTol` field lets the nodes in the previously mentioned region A change coordinates when slightly inside or outside the elements of region B. The change in coordinates causes the nodes of region A to assume the same surface as the nodes associated with the elements of region B. The constraint equations that relate the nodes at both regions of the interface are then written.

Solid elements with six degrees of freedom should only be interfaced with other six degree-of- freedom elements. The region A nodes should be near the region B elements. A location tolerance based on the smallest region B element length may be input. Stresses across the interface are not necessarily continuous. Nodes in the interface region should not have specified constraints.

Use the [[cpintf|CPINTF]] command to connect nodes by coupling instead of constraint equations. Use the [[eintf|EINTF]] command to connect nodes by line elements. See also the [[nsel|NSEL]] and [[esel|ESEL]] commands for selecting nodes and elements. See the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for a description of 3D space used to determine if a node will be considered by this command.

As an alternative to the **CEINTF** command, you can use contact elements and the internal multipoint constraint (MPC) algorithm to tie together two regions having dissimilar meshes. See [Solid-Solid and Shell-Shell Assemblies](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_solsol.html#) for more information.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CEINTF.html
