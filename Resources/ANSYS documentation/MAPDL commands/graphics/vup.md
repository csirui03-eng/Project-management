---
apdl: "/VUP"
method: vup
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.vup
generated: 2026-08-22
tags: [mapdl-command]
---

# /VUP

PyMAPDL: `mapdl.vup(wn='', label='', **kwargs)`

Specifies the global Cartesian coordinate system reference orientation.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**label**

Orientation:

- `Y` - Y vertical upward, X horizontal to the right, Z out from the screen (default).
- `-Y` - Y vertical downward, X horizontal to the left, Z out from the screen.
- `X` - X vertical upward, Y horizontal to the left, Z out from the screen.
- `-X` - X vertical downward, Y horizontal to the right, Z out from the screen.
- `Z` - Z vertical upward, Y horizontal to the right, X out from the screen. With this choice, you should use a view other than the [[view|/VIEW]] default of (0,0,1).
- `-Z` - Z vertical downward, Y horizontal to the left, X out from the screen. With this choice, you should use a view other than the [[view|/VIEW]] default of (0,0,1).

## Notes

Specifies the global Cartesian coordinate system reference orientation. The [[view|/VIEW]] and [[angle|/ANGLE]] commands may be used to reorient the view and are relative to this reference orientation. All coordinate systems are right-handed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VUP.html
