---
apdl: "DOF"
method: dof
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.dof
generated: 2026-08-22
tags: [mapdl-command]
---

# DOF

PyMAPDL: `mapdl.dof(lab1='', lab2='', lab3='', lab4='', lab5='', lab6='', lab7='', lab8='', lab9='', lab10='', **kwargs)`

Adds degrees of freedom to the current DOF set.

**Command default:**

Use degree of freedom set determined from element types.

## Parameters

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**, **lab6**, **lab7**, **lab8**, **lab9**, **lab10**: Valid labels are: UX, UY, UZ (structural displacements); ROTX, ROTY, ROTZ (structural rotations); TEMP, TBOT, TE2, TE3,..., TTOP (temperatures); PRES (pressure); VOLT (voltage); MAG (magnetic scalar potential); AZ (magnetic vector potential); CURR (current); EMF (electromotive force drop); CONC (concentration); DELETE.

## Notes

The degree of freedom (DOF) set for the model is determined from all element types defined. This command may be used to add to the current set. The ALL label may be used on some commands to represent all labels of the current degree of freedom set for the model. Issue the **DOF** command with no arguments to list the current set. Use the DELETE label to delete any previously added DOFs and return to the default DOF set.

**Product Restrictions**

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DOF.html
