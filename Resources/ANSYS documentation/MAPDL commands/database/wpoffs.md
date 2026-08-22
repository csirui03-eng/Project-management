---
apdl: "WPOFFS"
method: wpoffs
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wpoffs
generated: 2026-08-22
tags: [mapdl-command]
---

# WPOFFS

PyMAPDL: `mapdl.wpoffs(xoff='', yoff='', zoff='', **kwargs)`

Offsets the working plane.

## Parameters

**xoff**, **yoff**, **zoff**: Offset increments defined in the working plane coordinate system. If only `ZOFF` is used, the working plane will be redefined parallel to the present plane and offset by `ZOFF`.

## Notes

Changes the origin of the working plane by translating the working plane along its coordinate system axes.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPOFFS.html
