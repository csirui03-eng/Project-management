---
apdl: "PLTIME"
method: pltime
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.display.Display.pltime
generated: 2026-08-22
tags: [mapdl-command]
---

# PLTIME

PyMAPDL: `mapdl.pltime(tmin='', tmax='', **kwargs)`

Defines the time range for which data are to be displayed.

**Command default:**

Use the previously defined range ( [[timerange|TIMERANGE]] ).

## Parameters

**tmin**: Minimum time (defaults to the first point stored).

**tmax**: Maximum time (defaults to the last point stored).

## Notes

Defines the time (or frequency) range (within the range stored) for which data are to be displayed. Time is always displayed in the Z-axis direction for 3D graph displays. If XVAR = 1, time is also displayed in the X-axis direction and this control also sets the abscissa scale range.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLTIME.html
