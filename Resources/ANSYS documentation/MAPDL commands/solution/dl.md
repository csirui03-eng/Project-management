---
apdl: "DL"
method: dl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dl
generated: 2026-08-22
tags: [mapdl-command]
---

# DL

PyMAPDL: `mapdl.dl(line='', area='', lab='', value1='', value2='', **kwargs)`

Defines DOF constraints on lines.

## Parameters

**line**: Line at which constraints are to be specified. If ALL, apply to all selected lines ( [[lsel|LSEL]] ). If `LINE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `LINE`.

**area**: Area containing line. The normal to the symmetry or antisymmetry surface is assumed to lie on this area. Defaults to the lowest numbered selected area containing the line number.

**lab**

Symmetry label (see below) :

- `SYMM` - Generate symmetry constraints.
- `ASYM` - Generate antisymmetry constraints.

Mechanical APDL degree-of-freedom labels:

- `UX` - Displacement in X direction.
- `UY` - Displacement in Y direction.
- `UZ` - Displacement in Z direction.
- `ROTX` - Rotation about X axis.
- `ROTY` - Rotation about Y axis.
- `ROTZ` - Rotation about Z axis.
- `HDSP` - Hydrostatic pressure.
- `WARP` - Warping magnitude.
- `TEMP, TBOT, TE2, TE3, ..., TTOP` - Temperature
- `VOLT` - Electric scalar potential (see ).
- `AZ` - Magnetic vector potential in Z direction.
- `CONC` - Concentration.
- `ALL` - Applies all appropriate DOF labels except HDSP.

(table not available in the PyMAPDL source, see the Ansys help page)

**value1**: Value of DOF (real part) or table name reference on the line. Valid for all DOF labels. To specify a table, enclose the table name in % signs (for example, **DL**, `LINE`, `AREA`,TEMP,`tabname`). Use the [[dim|*DIM]] command to define a table.

**value2**

For VOLT DOFs:

Actual value of the imaginary component of the degree of freedom.

## Notes

You can transfer constraints from lines to nodes with the [[dtran|DTRAN]] or [[sbctran|SBCTRAN]] commands. See the [[dk|DK]] command for information about generating other constraints at lines.

Tabular boundary conditions ( `Value1` = `tabname`) are available only for the following degree of freedom labels: Electric (VOLT), Structural (UX, UY, UZ, ROTX, ROTY, ROTZ), Acoustic (PRES, UX, UY, UZ), and temperature (TEMP, TBOT, TE2, TE3,..., TTOP).

Constraints specified with this command can conflict with other specified constraints. For more information, see Resolution of Conflicting Constraint Specifications.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DL.html
