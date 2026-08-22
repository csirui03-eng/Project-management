---
apdl: "EDNROT"
method: ednrot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.ednrot
generated: 2026-08-22
tags: [mapdl-command]
---

# EDNROT

PyMAPDL: `mapdl.ednrot(option='', cid='', cname='', dof1='', dof2='', dof3='', dof4='', dof5='', dof6='', **kwargs)`

Applies a rotated coordinate nodal constraint in an explicit dynamics

analysis.

## Parameters

**option**

Label identifying the option to be performed:

ADD - Add a rotated nodal coordinate constraint (default).

DELE - Delete specified rotated nodal coordinate constraints.

LIST - List all rotated nodal coordinate constraints.

**cid**: Coordinate system ID for which rotated nodal constraints will be added or deleted. The CID must have been previously defined with the EDLCS command. If Option = DELE, use CID = ALL to delete all previously specified nodal constraints.

**cname**: Nodal component set to which the rotated coordinate constraint will be applied. Cname must be previously specified using the CM command.

**dof1, dof2, dof3, . . . , dof6**: Degrees of freedom for which the rotated nodal constraint will be applied. Valid degree of freedom labels include UX, UY, UZ, ROTX, ROTY, and ROTZ. If DOF1 = ALL, rotated nodal constraints will be applied to all degrees of freedom.

## Notes

Constraints applied with EDNROT are zero displacement constraints.

This command is also valid in SOLUTION.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
