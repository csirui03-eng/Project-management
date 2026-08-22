---
apdl: "PLDISP"
method: pldisp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.pldisp
generated: 2026-08-22
tags: [mapdl-command]
---

# PLDISP

PyMAPDL: `mapdl.pldisp(kund='', **kwargs)`

Displays the displaced structure.

## Parameters

**kund**

Undisplaced shape key:

- `0` - Display only displaced structure.
- `1` - Overlay displaced display with similar undisplaced display (appearance is system- dependent).
- `2` - Same as 1 except overlay with undisplaced edge display (appearance is system-dependent).

## Notes

Displays the displaced structure for the selected elements.

For information on true scale plots, refer to the description of the [[slashdscale|/DSCALE]] command ( [[slashdscale|/DSCALE]],,1.0).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLDISP.html
