---
apdl: "EDRC"
method: edrc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edrc
generated: 2026-08-22
tags: [mapdl-command]
---

# EDRC

PyMAPDL: `mapdl.edrc(option='', nrbf='', ncsf='', dtmax='', **kwargs)`

Specifies rigid/deformable switch controls in an explicit dynamic

analysis.

## Parameters

**option**

Label identifying option to be performed.

ADD - Define rigid/deformable controls (default).

DELE - Delete rigid/deformable controls.

LIST - List rigid/deformable controls.

**nrbf**

Flag to delete/activate nodal rigid bodies. If nodal rigid bodies or generalized weld definitions are active in the deformable bodies that are switched to rigid, then the definitions should be deleted to avoid instabilities.

0 - No change from previous status (default).

1 - Delete.

2 - Activate.

**ncsf**

Flag to delete/activate nodal constraint set. If nodal constraint/spotweld definitions are active in the deformable bodies that are switched to rigid, then the definitions should be deleted to avoid instabilities.

0 - No change from previous status (default).

1 - Delete.

2 - Activate.

**tdmax**: Maximum allowed time step after restart (no default).

## Notes

This command is only valid in an explicit dynamic small restart analysis (EDSTART,2). Use this command when you do a rigid/deformable switch (EDRD command) and you want to control constraints defined by other means for the deformable body (such as nodal constraints or a weld). For example, if a deformable body has nodal constraints defined and it is switched to a rigid body, the nodal constraints should be deleted since they are invalid for the rigid body. Later on, if you want to switch the rigid body to deformable again and retain the nodal constraints, you can use EDRC to activate the constraints previously defined for the deformable body. Otherwise, the nodal constraints remain deactivated.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
