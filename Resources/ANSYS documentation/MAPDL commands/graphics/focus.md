---
apdl: "/FOCUS"
method: focus
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.focus
generated: 2026-08-22
tags: [mapdl-command]
---

# /FOCUS

PyMAPDL: `mapdl.focus(wn='', xf='', yf='', zf='', ktrans='', **kwargs)`

Specifies the focus point (center of the window).

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**xf**, **yf**, **zf**: Location of the object to be at the focus point (center of the window) in the global Cartesian coordinate system. If `XF` = AUTO, allow automatic location calculation. If `XF` = USER, use focus location of last display (useful when last display had auto focus).

**ktrans**

Translate key:

- `0` - Interpret numerical `XF`, `YF`, `ZF` values as described above.
- `1` - Interpret `XF`, `YF`, `ZF` values as multiples of half-screens to translate from the current position in the screen coordinate system. Example: `XF` of 2.4 translates the display approximately 2.4 half-screens to the left in the screen X (horizontal) direction.
- `2` - Interpret `XF`, `YF`, `ZF` values as multiples of half-screens to translate from the current position in the global Cartesian coordinate system. Example: `XF` of 1.5 translates the display approximately 1.5 half-screens in the global Cartesian X direction of the model.

## Notes

Specifies the location on (or off) the model which is to be located at the focus point (center of the window). For section and capped displays, the cutting plane is also assumed to pass through this location (unless the working plane is used via [[cplane|/CPLANE]] ). See also [[auto|/AUTO]] and [[user|/USER]] commands.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FOCUS.html
