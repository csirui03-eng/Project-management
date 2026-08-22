---
apdl: "DSCALE"
method: dscale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dscale
generated: 2026-08-22
tags: [mapdl-command]
---

# DSCALE

PyMAPDL: `mapdl.dscale(rfact='', ifact='', tbase='', **kwargs)`

Scales DOF constraint values.

## Parameters

**rfact**: Scale factor for the real component. Zero (or blank) defaults to 1.0. Use a sma ll number for a zero scale factor.

**ifact**: Scale factor for the imaginary component. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**tbase**: Base temperature for temperature difference. For temperatures, the scale factor is applied to the temperature difference ( `T` - `TBASE` ) and then added to `TBASE`. `T` is the current temperature.

## Notes

Scales degree of freedom constraint values (displacement, temperature, etc.) in the database. If velocity and acceleration boundary conditions are applied in a structural analysis, they are also scaled by this command. Solid model boundary conditions are not scaled by this command, but boundary conditions on the FE model are scaled. Such scaled FE boundary conditions may still be overwritten by unscaled solid model boundary conditions if a subsequent boundary condition transfer occurs.

Scaling applies to the previously defined values for the selected nodes ( [[nsel|NSEL]] ) and the selected degree of freedom labels ( [[dofsel|DOFSEL]] ). Issue [[dlist|DLIST]] command to review results.

**DSCALE** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSCALE.html
