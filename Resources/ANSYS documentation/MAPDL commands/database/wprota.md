---
apdl: "WPROTA"
method: wprota
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wprota
generated: 2026-08-22
tags: [mapdl-command]
---

# WPROTA

PyMAPDL: `mapdl.wprota(thxy='', thyz='', thzx='', **kwargs)`

Rotates the working plane.

## Parameters

**thxy**: First rotation about the working plane Z axis (positive X toward Y).

**thyz**: Second rotation about working plane X axis (positive Y toward Z).

**thzx**: Third rotation about working plane Y axis (positive Z toward X).

## Notes

The specified angles (in degrees) are relative to the orientation of the working plane.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPROTA.html
