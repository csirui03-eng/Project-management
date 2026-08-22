---
apdl: "DJ"
method: dj
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dj
generated: 2026-08-22
tags: [mapdl-command]
---

# DJ

PyMAPDL: `mapdl.dj(elem='', label='', value='', **kwargs)`

Specifies boundary conditions on the components of relative motion of a joint element.

## Parameters

**elem**: Element number or ALL to be specified.

**label**

Valid labels are:

- `UX` - Displacement in local x direction.
- `UY` - Displacement in local y direction.
- `UZ` - Displacement in local z direction.
- `ROTX` - Rotation about local x axis.
- `ROTY` - Rotation about local y axis.
- `ROTZ` - Rotation about local y axis.
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

**value**: Value of the label.

## Notes

This command is valid for `MPC184` joint elements. See [[djdele|DJDELE]] for information about deleting boundary conditions applied via this command.

You can apply only one displacement, velocity, or acceleration load at any relative degree of freedom. If multiple loads are specified, the last applied load overrides the previous ones. For example, the following commands apply loads to element 100:

- D,100,UX, `Value`
- D,100,VELX, `Value`

In this case, the velocity load (VELX) applied in the last command will override the displacement load (UX).

Tabular boundary conditions ( `VALUE` = `tabname`) can be used.

%\_FIX% is a Mechanical APDL reserved table name. When `VALUE` is set to %\_FIX%, the program sprescribe the degree of freedom to the current relative displacement value. This option is only valid for the following labels: UX, UY, UZ, ROTX, ROTY, ROTZ. In most cases, %\_FIX% usage is efficient and recommended for all structural degrees of freedom.

In a modal analysis, the values of the eigenvectors at the degree of freedom connected via **DJ** may be insufficiently accurate to satisfy the **DJ** constraint conditions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DJ.html
