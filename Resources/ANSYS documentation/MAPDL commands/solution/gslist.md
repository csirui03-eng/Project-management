---
apdl: "GSLIST"
method: gslist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.gslist
generated: 2026-08-22
tags: [mapdl-command]
---

# GSLIST

PyMAPDL: `mapdl.gslist(lab='', **kwargs)`

When using generalized plane strain, lists the input data or solutions.

## Parameters

**lab**

Specify the content to be listed.

- `GEOMETRY` - List the data input using GSGDATA

- `BC` - List the data input using GSBDATA.

- `REACTIONS` - When the command is issued in POST1, list the reaction force at the ending point,

  and the moment about X and Y if the corresponding constraints were applied.

- `RESULTS` - When the command is issued in POST1, list the change of fiber length at the ending point during deformation and the rotation of the ending plane about X and Y during deformation.

- `ALL` - List all of the above (default).

## Notes

This command can be used to list the initial position of the ending plane, the applied load or displacements in the fiber direction, the resulting position of the ending plane after deformation, and the available reaction forces and moments at the ending point.

All inputs and outputs are in the global Cartesian coordinate system. For more information about the generalized plane strain feature, see Generalized Plane Strain Option of Current-Technology Solid Elements in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSLIST.html
