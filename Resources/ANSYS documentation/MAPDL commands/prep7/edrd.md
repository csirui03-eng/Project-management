---
apdl: "EDRD"
method: edrd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.explicit_dynamics.ExplicitDynamics.edrd
generated: 2026-08-22
tags: [mapdl-command]
---

# EDRD

PyMAPDL: `mapdl.edrd(option='', part='', mrb='', **kwargs)`

Switches a part from deformable to rigid or from rigid to deformable in

an explicit dynamic analysis.

## Parameters

**option**

Label identifying the option to be performed.

D2R - Change specified part from deformable to rigid (default).

R2D - Change specified part from rigid to deformable. Use this option to switch a  
part back to a deformable state after it has been changed to rigid using EDRD,D2R.

LIST - List parts that are flagged to change from deformable to rigid or rigid to  
deformable.

**part**: Part number for part to be changed (no default).

**mrb**: Part number of the master rigid body to which the part is merged. MRB is used only if Option = D2R. If MRB = 0 (which is the default), the part becomes an independent rigid body.

## Notes

This command is valid in a new explicit dynamic analysis or in a restart. It is only possible to switch parts (D2R or R2D) in a restart if part switching is first activated in the original analysis. If part switching is not required in the original analysis but will be used in the restart, you must issue EDRD,D2R with no further arguments in the original analysis. You can use the EDRI command to define inertia properties for newly created rigid bodies (D2R).

Parts that are defined as rigid using EDMP,RIGID are permanently rigid and cannot be changed to deformable.

This command is also valid in PREP7.

Distributed ANSYS Restriction: This command is not supported in Distributed ANSYS.
