---
apdl: "XVAR"
method: xvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.display.Display.xvar
generated: 2026-08-22
tags: [mapdl-command]
---

# XVAR

PyMAPDL: `mapdl.xvar(n='', **kwargs)`

Specifies the X variable to be displayed.

## Parameters

**n**

X variable number:

- `0 or 1` - Display [[plvar|PLVAR]] values vs. time (or frequency).
- `n` - Display [[plvar|PLVAR]] values vs. variable `n` (2 to `NV` ( [[numvar|NUMVAR]] )).
- `1` - Interchange time and [[plvar|PLVAR]] variable numbers with time as the curve parameter. [[plvar|PLVAR]] variable numbers are displayed uniformly spaced along X-axis from position 1 to 10.

## Notes

Defines the X variable (displayed along the abscissa) against which the Y variable(s) ( [[plvar|PLVAR]] ) are to be displayed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XVAR.html
