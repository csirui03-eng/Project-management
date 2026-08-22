---
apdl: "DA"
method: da
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.da
generated: 2026-08-22
tags: [mapdl-command]
---

# DA

PyMAPDL: `mapdl.da(area='', lab='', value1='', value2='', **kwargs)`

Defines degree-of-freedom constraints on areas.

## Parameters

**area**: Area on which constraints are to be specified. If ALL, apply to all selected areas ( [[asel|ASEL]] ). If `AREA` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `AREA`.

**lab**

Symmetry label (see below) :

- `SYMM` - Generate symmetry constraints. Requires no `Value1` or `Value2`.
- `ASYM` - Generate antisymmetry constraints. Requires no `Value1` or `Value2`.

Mechanical APDL degree-of-freedom labels:

- `UX` - Displacement in X direction.
- `UY` - Displacement in Y direction.
- `UZ` - Displacement in Z direction.
- `ROTX` - Rotation about X axis.
- `ROTY` - Rotation about Y axis.
- `ROTZ` - Rotation about Z axis.
- `HDSP` - Hydrostatic pressure.
- `PRES` - Pressure.
- `TEMP, TBOT, TE2, TE3, ..., TTOP` - Temperature.
- `MAG` - Magnetic scalar potential (see below).
- `VOLT` - Electric scalar potential (see below).
- `AZ` - Magnetic vector potential in Z direction (see below).
- `CONC` - Concentration.
- `ALL` - Applies all appropriate degree-of-freedom labels except HDSP.

(table not available in the PyMAPDL source, see the Ansys help page)

**value1**: Value of degree of freedom or table name reference on the area. Valid for all degree-of-freedom labels. To specify a table, enclose the table name in % signs (for example, **DA**, `AREA`,TEMP,`tabname`). Use the [[dim|*DIM]] command to define a table.

**value2**

For MAG and VOLT degrees of freedom:

Value of the imaginary component of the degree of freedom.

## Notes

You can transfer constraints from areas to nodes via [[dtran|DTRAN]] or [[sbctran|SBCTRAN]]. See [[dk|DK]] for information about generating other constraints on areas.

Tabular boundary conditions ( `VALUE` = `tabname`) are available only for the following degree- of-freedom labels: Electric (VOLT), Structural (UX, UY, UZ, ROTX, ROTY, ROTZ), Acoustic (PRES, UX, UY, UZ), and temperature (TEMP, TBOT, TE2, TE3,..., TTOP).

Constraints specified by the **DA** command can conflict with other specified constraints. See Resolution of Conflicting Constraint Specifications in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DA.html
