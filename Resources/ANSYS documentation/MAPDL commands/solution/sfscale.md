---
apdl: "SFSCALE"
method: sfscale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfscale
generated: 2026-08-22
tags: [mapdl-command]
---

# SFSCALE

PyMAPDL: `mapdl.sfscale(lab='', fact='', fact2='', **kwargs)`

Scales surface loads on elements.

## Parameters

**lab**

Valid surface load label. If ALL, use all appropriate labels.

(table not available in the PyMAPDL source, see the Ansys help page)

Thermal labels CONV and HFLUX are mutually exclusive.

**fact**: Scale factor for the first surface load value. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

**fact2**: Scale factor for the second surface load value. Zero (or blank) defaults to 1.0. Use a small number for a zero scale factor.

## Notes

Scales surface loads (pressure, convection, etc.) in the database on the selected elements. Surface loads are applied with the [[sf|SF]], [[sfe|SFE]], or [[sfbeam|SFBEAM]] commands. Issue the [[sfelist|SFELIST]] command to list the surface loads. Solid model boundary conditions are not scaled by this command, but boundary conditions on the FE model are scaled.

Such scaled FE boundary conditions may still be overwritten by unscaled solid model boundary conditions if a subsequent boundary condition transfer occurs.

**SFSCALE** does not work for tabular boundary conditions.

This command is also valid in PREP7 and in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFSCALE.html
