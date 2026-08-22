---
apdl: "RBE3"
method: rbe3
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.rbe3
generated: 2026-08-22
tags: [mapdl-command]
---

# RBE3

PyMAPDL: `mapdl.rbe3(independ='', dof='', depend='', wtfact='', **kwargs)`

Distributes the force/moment applied at an independent node to a set of dependent nodes.

## Parameters

**independ**: Node at which the force/moment to be distributed will be applied (the independent node). To be included in the degree-of-freedom (DOF) solution, this node must be associated with an element.

**dof**: Refers to the independent node DOFs to be used in the constraint equations. Valid labels are: UX, UY, UZ, ROTX, ROTY, ROTZ, UXYZ, RXYZ, ALL

**depend**: The name of an array parameter that contains a list of dependent nodes. Must specify the starting index number. ALL can be used for the currently selected set of nodes. The dependent nodes must not be colinear (that is, must not be located on the same straight line). See [[rbe3#Notes|RBE3]] for details.

**wtfact**: The name of an array parameter that contains a list of weighting factors corresponding to each dependent node defined by Depend. Must have the starting index number. If not specified, the weighting factor for each dependent node defaults to 1.

## Notes

**RBE3** distributes the force/moment applied at an independent node to a set of dependent nodes, taking into account the geometry of the dependent nodes as well as weighting factors. The force is distributed to the dependent nodes proportional to the weighting factors. The moment is distributed as forces to the dependent nodes; these forces are proportional to the distance from the center of gravity of the dependent nodes times the weighting factors. Only the translational degrees of freedom of the dependent nodes are used for constructing the constraint equations. Constraint equations are converted to distributed forces/moments on the dependent nodes during solution.

**RBE3** creates constraint equations such that the motion of the independent node is the average of the dependent nodes. For the rotations, a least-squares approach is used to define the "average rotation" at the independent node from the translations of the dependent nodes. If the dependent nodes are colinear, then one of the independent node rotations that is parallel to the colinear direction cannot be determined in terms of the translations of the dependent nodes. Therefore, the associated moment component on the independent node in that direction cannot be transmitted. When this case occurs, a warning message is issued and the constraint equations created by **RBE3** are ignored.

Applying this command to a large number of dependent nodes may result in constraint equations with a large number of coefficients. This may significantly increase the peak memory required during the process of element assembly. If real memory or virtual memory is not available, consider reducing the number of dependent nodes.

You can use the [[dofsel|DOFSEL]] command to select the degrees of freedom (DOFs) of the dependent nodes to be included in the resulting constraint equations. (Be sure to issue [[dofsel|DOFSEL]],ALL after issuing **RBE3**.) This capability is useful if, for example, you want to ignore radial constraints in cylindrical geometries. The selected DOFs must collectively generate forces and moments on the independent node in all six DOFs.

**RBE3** is restricted to small-deflection analysis (large-deflection is not supported). As an alternative to **RBE3**, you can apply a similar type of constraint using contact elements and the internal multipoint constraint (MPC) algorithm. For more information, see [Surface-based Constraints](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_surfcon.html#strbeamso1703).

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RBE3.html
