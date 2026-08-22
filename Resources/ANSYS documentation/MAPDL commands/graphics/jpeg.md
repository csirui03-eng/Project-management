---
apdl: "JPEG"
method: jpeg
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.jpeg
generated: 2026-08-22
tags: [mapdl-command]
---

# JPEG

PyMAPDL: `mapdl.jpeg(kywrd='', opt='', **kwargs)`

Provides JPEG file export for Mechanical APDL displays.

## Parameters

**kywrd**

Specifies various JPEG file export options.

- `QUAL` - If `Kywrd` = QUAL, then `OPT` is an integer value defining the JPEG quality index on an arbitrary scale ranging from 1 to 100. The default value is 75.
- `ORIENT` - If `Kywrd` = ORIENT, then `OPT` will determine the orientation of the entire plot. `OPT` can be either Horizontal (default) or Vertical.
- `COLOR` - If `Kywrd` = COLOR, then `OPT` will determine the color depth of the saved file. `OPT` can be 0, 1, or 2, corresponding to Black and White, Grayscale, and Color (default), respectively.
- `TMOD` - If `Kywrd` = TMOD, then `OPT` will determine the text method. `OPT` can be either 1 or 0, corresponding to bitmap text (default) or line stroke text, respectively.
- `DEFAULT` - If `Kywrd` = DEFAULT, then all of the default values, for all of the Kywrd parameters listed above, are active.

**opt**

`OPT` can have the following names or values, depending on the value for `Kywrd` (see above).

- `1 to 100` - If `Kywrd` = QUAL, a value between 1 and 100 will determine the quality index of the JPEG file.
- `Horizontal, Vertical` - If `Kywrd` = ORIENT, the terms Horizontal or Vertical determine the orientation of the plot.
- `0,1,2` - If `Kywrd` = COLOR, the numbers 0, 1, and 2 correspond to Black and White, Grayscale and Color, respectively.
- `1,0` - If `Kywrd` = TMOD, the values 1 and 0 determine whether bitmap (1) or stroke text (0) fonts will be used

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_JPEG.html
