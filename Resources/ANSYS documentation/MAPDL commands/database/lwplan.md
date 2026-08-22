---
apdl: "LWPLAN"
method: lwplan
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.lwplan
generated: 2026-08-22
tags: [mapdl-command]
---

# LWPLAN

PyMAPDL: `mapdl.lwplan(wn='', nl1='', ratio='', **kwargs)`

Defines the working plane normal to a location on a line.

## Parameters

**wn**: Window number whose viewing direction will be modified to be normal to the working plane (defaults to 1). If `WN` is a negative value, the viewing direction will not be modified.

**nl1**: Number of line to be used. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**ratio**: Location on `NL1`, specified as a ratio of the line length. Must be between 0.0 and 1.0. If `RATIO` = P, use graphical picking to specify location on the line.

## Notes

Defines a working plane (to assist in picking operations) normal to a location on a line. See [[wpstyl|WPSTYL]] command to set the style of working plane display.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LWPLAN.html
