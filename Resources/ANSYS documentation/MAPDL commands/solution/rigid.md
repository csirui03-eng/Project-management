---
apdl: "RIGID"
method: rigid
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.rigid
generated: 2026-08-22
tags: [mapdl-command]
---

# RIGID

PyMAPDL: `mapdl.rigid(dof1='', dof2='', dof3='', dof4='', dof5='', dof6='', **kwargs)`

Specifies known rigid body modes (if any) of the model.

## Parameters

**dof1**, **dof2**, **dof3**, **dof4**, **dof5**, **dof6**: Up to six global Cartesian directions of the rigid modes. For a completely free 2D model, use ALL or UX, UY, ROTZ. For a completely free 3D model, use ALL or UX, UY, UZ, ROTX, ROTY, ROTZ. For a constrained model, use UX, UY, UZ, ROTX, ROTY, or ROTZ, as appropriate, to specify each and every unconstrained direction which exists in the model (not specifying every direction may cause difficulties in extracting the modes).

## Notes

Specifies known rigid body modes (if any) of the model. This command applies only to a component mode synthesis (CMS) analysis (see the [[cmsopt|CMSOPT]] command). Any rigid body modes specified must be permitted by the applied displacement constraints (that is, do not specify a rigid body mode in a constrained direction). Reissue the command to redefine the specification. If used in SOLUTION, this command is valid only within the first load step.

This command is also valid in PREP7. Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RIGID.html
