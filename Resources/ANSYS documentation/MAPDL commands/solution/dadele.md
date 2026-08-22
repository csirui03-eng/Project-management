---
apdl: "DADELE"
method: dadele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dadele
generated: 2026-08-22
tags: [mapdl-command]
---

# DADELE

PyMAPDL: `mapdl.dadele(area='', lab='', **kwargs)`

Deletes degree-of-freedom constraints on an area.

## Parameters

**area**: Area for which constraints are to be deleted. If ALL, delete for all selected areas ( [[asel|ASEL]] ). If `AREA` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). You can substitute a component name for `AREA`.

**lab**

Valid constraint labels are:

- `ALL` - All constraints.
- `SYMM` - Symmetry constraints.
- `ASYM` - Antisymmetry constraints.
- `UX` - Displacement in X direction.
- `UY` - Displacement in Y direction.
- `UZ` - Displacement in Z direction.
- `ROTX` - Rotation about X axis.
- `ROTY` - Rotation about Y axis.
- `ROTZ` - Rotation about Z axis.
- `PRES` - Pressure.
- `TEMP, TBOT, TE2, TE3, ..., TTOP` - Temperature.
- `MAG` - Magnetic scalar potential.
- `VOLT` - Electric scalar potential.
- `AZ` - Magnetic vector potential in Z direction (see notes).
- `CONC` - Concentration.

## Notes

Deletes the degree of freedom constraints at an area (and all corresponding finite element constraints) previously specified with the [[da|DA]] command. See the [[ddele|DDELE]] command for delete details.

If the multiple species labels have been changed to user-defined labels via the MSSPEC command, use the user-defined labels.

See the [[da|DA]] or the [[da|DA]] commands for details on element applicability.

> [!WARNING]
> On previously meshed areas, **all** constraints on affected nodes will be deleted, whether or not they were specified by the [[da|DA]] command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DADELE.html
