---
apdl: "/SMBC"
method: smbc
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.smbc
generated: 2026-08-22
tags: [mapdl-command]
---

# /SMBC

PyMAPDL: `mapdl.smbc(mode='', **kwargs)`

Controls the display of solid model boundary condition symbols and labels.

## Parameters

**mode**

- `CENT` - Solid model boundary condition symbols and labels appear at the centroid of the solid model entity (default).
- `TESS` - Solid model boundary condition symbols and labels appear inside each constituent element of the tessellation.

## Notes

`Mode` = CENT is designed to reduce the clutter of boundary condition symbols in solid model plots. For example, if you have assigned normal pressure loads to an area, you may choose to display the pressures as arrows with the [[psf|/PSF]] command using [[psf|/PSF]],PRES,NORM,2. When `Mode` = CENT, the pressure arrow is displayed at the centroid of the area. When `Mode` = TESS, a pressure arrow is displayed at the centroid of each polygon of the area's tessellation.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SMBC_sl.html
