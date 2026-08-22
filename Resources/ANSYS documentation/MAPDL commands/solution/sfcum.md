---
apdl: "SFCUM"
method: sfcum
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfcum
generated: 2026-08-22
tags: [mapdl-command]
---

# SFCUM

PyMAPDL: `mapdl.sfcum(lab='', oper='', fact='', fact2='', **kwargs)`

Specifies that surface loads are to be accumulated.

## Parameters

**lab**

Valid surface load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

**oper**

Accumulation key:

- `REPL` - Subsequent values replace the previous values (default).
- `ADD` - Subsequent values are added to the previous values.
- `IGNO` - Subsequent values are ignored.

**fact**: Scale factor for the first surface load value. A (blank) or '0' entry defaults to 1.0.

**fact2**: Scale factor for the second surface load value. A (blank) or '0' entry defaults to 1.0.

## Notes

Allows repeated surface loads (pressure, convection, etc.) to be replaced, added, or ignored. Surface loads are applied with the [[sf|SF]], [[sfe|SFE]], and [[sfbeam|SFBEAM]] commands. Issue the [[sfelist|SFELIST]] command to list the surface loads. The operations occur when the next surface load specifications are defined. For example, issuing the [[sf|SF]] command with a pressure value of 25 after a previous [[sf|SF]] command with a pressure value of 20 causes the current value of that pressure to be 45 with the add operation, 25 with the replace operation, or 20 with the ignore operation. All new pressures applied with [[sf|SF]] after the ignore operation will be ignored, even if no current pressure exists on that surface.

Scale factors are also available to multiply the next value before the add or replace operation. A scale factor of 2.0 with the previous "add" example results in a pressure of 70. Scale factors are applied even if no previous values exist. Issue **SFCUM**,STAT to show the current label, operation, and scale factors. Solid model boundary conditions are not affected by this command, but boundary conditions on the FE model are affected.

The FE boundary conditions may still be overwritten by existing solid model boundary conditions if a subsequent boundary condition transfer occurs.

**SFCUM** does not work for tabular boundary conditions.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFCUM.html
