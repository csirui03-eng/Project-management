---
apdl: "TIFF"
method: tiff
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.tiff
generated: 2026-08-22
tags: [mapdl-command]
---

# TIFF

PyMAPDL: `mapdl.tiff(kywrd='', opt='', **kwargs)`

Provides TIFF file export for Mechanical APDL displays.

## Parameters

**kywrd**

Specifies various TIFF file export options.

- `COMP` - If `Kywrd` = COMP, then `OPT` controls data compression for the output file. If COMP = 0, then compression is off. If COMP = 1 (default), then compression is on.
- `ORIENT` - If `Kywrd` = ORIENT, then `OPT` will determine the orientation of the entire plot. `OPT` can be either Horizontal (default) or Vertical.
- `COLOR` - If `Kywrd` = COLOR, then `OPT` will determine the color attribute of the saved file. `OPT` can be 0, 1, or 2, corresponding to Black and White, Grayscale, and Color (default), respectively.
- `TMOD` - If `Kywrd` = TMOD, then `OPT` will determine the text method. `OPT` can be either 1 or 0, corresponding to bitmap text (default) or line stroke text, respectively.
- `DEFAULT` - If `Kywrd` = DEFAULT, then all of the default values, for all of the Kywrd parameters listed above, are active.

**opt**

`OPT` can have the following names or values, depending on the value for `Kywrd` (see above).

- `1 or 0` - If `Kywrd` = COMP, a value or 1 (on) or 0 (off) will control compression for the TIFF file.
- `Horizontal, Vertical` - If `Kywrd` = ORIENT, the terms Horizontal or Vertical determine the orientation of the plot.
- `0, 1, 2` - If `Kywrd` = COLOR, the numbers 0, 1, and 2 correspond to Black and White, Grayscale and Color, respectively.
- `1, 0` - If `Kywrd` = TMOD, the values 1 and 0 determine whether bitmap (1) or stroke text (0) fonts will be used

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TIFF.html
