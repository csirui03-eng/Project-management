---
apdl: "FCUM"
method: fcum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.fcum
generated: 2026-08-22
tags: [mapdl-command]
---

# FCUM

PyMAPDL: `mapdl.fcum(oper='', rfact='', ifact='', **kwargs)`

Specifies that force loads are to be accumulated.

## Parameters

**oper**

Accumulation key:

- `REPL` - Subsequent values replace the previous values (default).
- `ADD` - Subsequent values are added to the previous values.
- `IGNO` - Subsequent values are ignored.

**rfact**: Scale factor for the real component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**ifact**: Scale factor for the imaginary component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

## Notes

Allows repeated force load (force, heat flow, etc.) values to be replaced, added, or ignored. Operations apply to the selected nodes \[NSEL\]. and the force labels corresponding to the selected force labels ( [[dofsel|DOFSEL]] ). The operations occur when the next force specifications are defined. For example, issuing the command [[f|F]],1,FX,250 after a previous [[f|F]],1,FX,200 causes the current value of the force on node 1 in the x-direction to be 450 with the add operation, 250 with the replace operation, or 200 with the ignore operation. Scale factors are also available to multiply the next value before the add or replace operation. A scale factor of 2.0 with the previous "add" example results in a force of 700. Scale factors are applied even if no previous values exist. Issue **FCUM**,STAT to show the current label, operation, and scale factors. Solid model boundary conditions are not affected by this command, but boundary conditions on the FE model are affected. FE boundary conditions may still be overwritten by existing solid model boundary conditions if a subsequent boundary condition transfer occurs.

**FCUM** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FCUM.html
