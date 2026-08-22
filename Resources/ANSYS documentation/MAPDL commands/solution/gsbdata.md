---
apdl: "GSBDATA"
method: gsbdata
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.gsbdata
generated: 2026-08-22
tags: [mapdl-command]
---

# GSBDATA

PyMAPDL: `mapdl.gsbdata(labz='', valuez='', labx='', valuex='', laby='', valuey='', **kwargs)`

Specifies the constraints or applies the load at the ending point for generalized plane strain option.

## Parameters

**labz**

Constraint or load at the ending point in the fiber Z direction.

- `F` - Apply a force in the fiber direction (default).
- `LFIBER` - Define a length change in the fiber direction.

**valuez**: Value for `LabZ`. The default is zero.

**labx**

Constraint or load on rotation about X.

- `MX` - Supply a moment to cause the rotation of the ending plane about X (default).
- `ROTX` - Define a rotation angle (in radians) of the ending plane about X.

**valuex**: Value for `LabX`. The default is zero.

**laby**

Constraint or load on rotation about Y

- `MY` - Supply a moment to cause the rotation of the ending plane about Y (default).
- `ROTY` - Define a rotation angle (in radians) of the ending plane about Y.

**valuey**: Value for `LabY`. The default is zero.

## Notes

All inputs are in the global Cartesian coordinate system. For more information about the generalized plane strain feature, see Generalized Plane Strain Option of Current-Technology Solid Elements in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSBDATA.html
