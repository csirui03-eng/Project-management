---
apdl: "DCUM"
method: dcum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dcum
generated: 2026-08-22
tags: [mapdl-command]
---

# DCUM

PyMAPDL: `mapdl.dcum(oper='', rfact='', ifact='', tbase='', **kwargs)`

Specifies that DOF constraint values are to be accumulated.

**Command default:**

Replace previous values.

## Parameters

**oper**

Accumulation key:

- `REPL` - Subsequent values replace the previous values (default).
- `ADD` - Subsequent values are added to the previous values.
- `IGNO` - Subsequent values are ignored.

**rfact**: Scale factor for the real component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**ifact**: Scale factor for the imaginary component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**tbase**: Base temperature for temperature difference. Used only with temperature degree of freedom. Scale factor is applied to the temperature difference ( `T` - `TBASE` ) and then added to `TBASE`. `T` is the current temperature.

## Notes

Allows repeated degree of freedom constraint values (displacement, temperature, etc.) to be replaced, added, or ignored. Operations apply to the selected nodes ( [[nsel|NSEL]] ) and the selected degree of freedom labels ( [[dofsel|DOFSEL]] ). This command also operates on velocity and acceleration loads applied in a structural analysis.

The operations occur when the next degree of freedom constraints are defined. For example, issuing the command [[d|D]],1,UX,.025 after a previous [[d|D]],1,UX,.020 causes the new value of the displacement on node 1 in the x-direction to be 0.045 with the add operation, 0.025 with the replace operation, or 0.020 with the ignore operation. Scale factors are also available to multiply the next value before the add or replace operation. A scale factor of 2.0 with the previous "add" example results in a displacement of 0.070. Scale factors are applied even if no previous values exist. Issue **DCUM**,STAT to show the current label, operation, and scale factors. Solid model boundary conditions are not affected by this command, but boundary conditions on the FE model are affected. FE boundary conditions may still be overwritten by existing solid model boundary conditions if a subsequent boundary condition transfer occurs.

**DCUM** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DCUM.html
