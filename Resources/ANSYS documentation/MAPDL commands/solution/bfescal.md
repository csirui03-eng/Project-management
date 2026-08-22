---
apdl: "BFESCAL"
method: bfescal
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_body_loads.FeBodyLoads.bfescal
generated: 2026-08-22
tags: [mapdl-command]
---

# BFESCAL

PyMAPDL: `mapdl.bfescal(lab='', fact='', tbase='', **kwargs)`

Scales element body-force loads.

## Parameters

**lab**

Valid body load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**fact**: Scale factor for the element body load values. Zero (or blank) defaults to 1.0. Use a small number for a "zero" scale factor. The scale factor is not applied to body load phase angles.

**tbase**: Base temperature for temperature difference. Used only with `Lab` = TEMP. Scale factor is applied to the temperature difference ( `T` - `TBASE` ) and then added to `TBASE`. `T` is the current temperature.

## Notes

Scales element body-force loads on the selected elements in the database. Issue the [[bfelist|BFELIST]] command to list the element body loads. Solid model boundary conditions are not scaled by this command, but boundary conditions on the FE model are scaled. (Note that such scaled FE boundary conditions may still be overwritten by unscaled solid model boundary conditions if a subsequent boundary condition transfer occurs.)

**BFESCAL** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BFESCAL.html
