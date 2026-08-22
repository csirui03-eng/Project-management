---
apdl: "/DIST"
method: dist
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.dist
generated: 2026-08-22
tags: [mapdl-command]
---

# /DIST

PyMAPDL: `mapdl.dist(wn='', dval='', kfact='', **kwargs)`

Specifies the viewing distance for magnifications and perspective.

**Command default:**

Distance is automatically calculated to produce full window magnification.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**dval**: Distance along the view line from the observer to the focus point (defaults to value producing full- window display). Distances "too close" to the object will produce excessive magnifications. If `DVAL` = AUTO, zero, or blank, the program will calculate the distance automatically. If `DVAL` = USER, the distance of last display will be used (useful when last display automatically calculated distance).

**kfact**

`DVAL` interpretation key:

- `0` - Interpret numerical `DVAL` values as described above.
- `1` - Interpret `DVAL` as a multiplier on the current distance ( `DVAL` of 2 gives twice the current distance; 0.5 gives half the current distance, etc.).

## Notes

The scale factor is relative to the window shape. For example, for objects centered in a square window and with parallel projection (no perspective), a distance of (equation omitted) /2 (+10%) producesa full window magnification, where (equation omitted) isthe largest in-plane vertical or horizontal dimension. See also [[auto|/AUTO]] and [[user|/USER]] commands.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DIST.html
