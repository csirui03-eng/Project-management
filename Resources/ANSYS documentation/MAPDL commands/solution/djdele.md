---
apdl: "DJDELE"
method: djdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.djdele
generated: 2026-08-22
tags: [mapdl-command]
---

# DJDELE

PyMAPDL: `mapdl.djdele(elem='', lab='', **kwargs)`

Deletes boundary conditions on the components of relative motion of a joint element.

## Parameters

**elem**: Element number or ALL. ALL (or leaving this field blank) will delete all joint element boundary conditions specified by `LAB`.

**lab**

Valid labels are:

- `UX` - Displacement in local x direction.
- `UY` - Displacement in local y direction.
- `UZ` - Displacement in local z direction.
- `ROTX` - Rotation about local x axis.
- `ROTY` - Rotation about local y axis.
- `ROTZ` - Rotation about local z axis.
- `VELX` - Linear velocity in local x direction.
- `VELY` - Linear velocity in local y direction.
- `VELZ` - Linear velocity in local z direction.
- `OMGX` - Angular velocity in local x direction.
- `OMGY` - Angular velocity in local y direction.
- `OMGZ` - Angular velocity in local z direction.
- `ACCX` - Linear acceleration in local x direction.
- `ACCY` - Linear acceleration in local y direction.
- `ACCZ` - Linear acceleration in local z direction.
- `DMGX` - Angular acceleration in local x direction.
- `DMGY` - Angular acceleration in local y direction.
- `DMGZ` - Angular acceleration in local z direction.
- `ALL, or (blank)` - Delete all applied boundary conditions.

## Notes

This command is valid for `MPC184` joint elements. See [[dj|DJ]] for information on specifying boundary conditions on the components of relative motion of a joint element.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DJDELE.html
