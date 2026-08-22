---
apdl: "DK"
method: dk
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dk
generated: 2026-08-22
tags: [mapdl-command]
---

# DK

PyMAPDL: `mapdl.dk(kpoi='', lab='', value='', value2='', kexpnd='', lab2='', lab3='', lab4='', lab5='', lab6='', **kwargs)`

Defines DOF constraints at keypoints.

## Parameters

**kpoi**: Keypoint at which constraint is to be specified. If ALL, apply to all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

**lab**: Additional degree of freedom labels. The same values are applied to the keypoints for these labels.

**value**: Degree of freedom value or table name reference for tabular boundary conditions. To specify a table, enclose the table name in percent signs (%) (for example, **DK**,NODE,TEMP,`tabname`). Use the [[dim|*DIM]] command to define a table.

**value2**: Second degree of freedom value (if any). If the analysis type and the degree of freedom allow a complex input, `VALUE` (above) is the real component and `VALUE2` is the imaginary component.

**kexpnd**

Expansion key:

- `0` - Constraint applies only to the node at this keypoint.
- `1` - Flags this keypoint for constraint expansion.

**lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Additional degree of freedom labels. The same values are applied to the keypoints for these labels.

## Notes

A keypoint may be flagged using `KEXPND` to allow its constraints to be expanded to nodes on the attached solid model entities having similarly flagged keypoint constraints. Constraints are transferred from keypoints to nodes with the [[dtran|DTRAN]] or [[sbctran|SBCTRAN]] commands. The expansion uses interpolation to apply constraints to the nodes on the lines between flagged keypoints. If all keypoints of an area or volume region are flagged and the constraints (label and values) are equal, the constraints are applied to the interior nodes of the region. See the [[d|D]] command for a description of nodal constraints.

Tabular boundary conditions ( `VALUE` = `tabname`) are available only for the following degree of freedom labels: Electric (VOLT), structural (UX, UY, UZ, ROTX, ROTY, ROTZ), Acoustic (PRES, UX, UY, UZ), and temperature (TEMP, TBOT, TE2, TE3,..., TTOP).

Constraints specified by the **DK** command can conflict with other specified constraints. See Resolution of Conflicting Constraint Specifications in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DK.html
