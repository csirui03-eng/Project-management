---
apdl: "DLDELE"
method: dldele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dldele
generated: 2026-08-22
tags: [mapdl-command]
---

# DLDELE

PyMAPDL: `mapdl.dldele(line='', lab='', **kwargs)`

Deletes DOF constraints on a line.

## Parameters

**line**: Line for which constraints are to be deleted. If ALL, delete for all selected lines ( [[lsel|LSEL]] ). If `LINE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `LINE`

**lab**

Constraint label:

- `ALL` - All constraints.
- `SYMM` - Symmetry constraints.
- `ASYM` - Antisymmetry constraints.
- `UX` - Displacement in X direction.
- `UY` - Displacement in Y direction.
- `UZ` - Displacement in Z direction.
- `ROTX` - Rotation about X axis.
- `ROTY` - Rotation about Y axis.
- `ROTZ` - Rotation about Z axis.
- `WARP` - Warping magnitude.
- `PRES` - Pressure.
- `TEMP, TBOT, TE2, TE3, ..., TTOP` - Temperature.
- `VOLT` - Electric scalar potential.
- `AZ` - Magnetic vector potential in Z direction.
- `CONC` - Concentration.

## Notes

Deletes the degree of freedom constraints (and all corresponding finite element constraints) on a line previously specified with the [[dl|DL]] command. See the [[ddele|DDELE]] command for delete details.

> [!WARNING]
> On previously meshed lines, all constraints on affected nodes will also be deleted, whether or not they were specified by the [[dl|DL]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DLDELE.html
