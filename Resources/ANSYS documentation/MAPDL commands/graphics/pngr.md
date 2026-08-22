---
apdl: "PNGR"
method: pngr
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.pngr
generated: 2026-08-22
tags: [mapdl-command]
---

# PNGR

PyMAPDL: `mapdl.pngr(kywrd='', opt='', val='', **kwargs)`

Provides PNG file export for Mechanical APDL displays.

## Parameters

**kywrd**

Specifies various PNG file export options.

- `COMP` - If `Kywrd` = COMP, then `OPT` is either ON or OFF (blank is interpreted as OFF). This option allows you to turn PNG file compression ON or OFF. If OPT = ON, then The VAL field is read to determine the degree of compression. See the VALUE argument for acceptable compression values.
- `ORIENT` - If `Kywrd` = ORIENT, then `OPT` will determine the orientation of the entire plot. `OPT` can be either Horizontal (default) or Vertical.
- `COLOR` - If `Kywrd` = COLOR, then `OPT` will determine the color depth of the saved file. `OPT` can be 0, 1, or 2, corresponding to Black and White, Grayscale, and Color (default), respectively.
- `TMOD` - If `Kywrd` = TMOD, then `OPT` will determine the text method. `OPT` can be either 1 or 0, corresponding to bitmap text (default) or line stroke text, respectively.
- `DEFAULT` - If `Kywrd` = DEFAULT, then all of the default values, for all of the Kywrd parameters listed above, are active.
- `STAT` - Shows the current status of PNG file export.

**opt**

`OPT` can have the following names or values, depending on the value for `Kywrd` (see above).

- `ON, OFF` - If `Kywrd` = COMP, the values On and Off control the use of compression. The degree of compression is determined by VAL
- `Horizontal, Vertical` - If `Kywrd` = ORIENT, the terms Horizontal or Vertical determine the orientation of the plot.
- `0, 1, 2` - If `Kywrd` = COLOR, the numbers 0, 1, and 2 correspond to Black and White, Grayscale and Color, respectively.
- `1, 0` - If `Kywrd` = TMOD, the values 1 and 0 determine whether bitmap (1) or stroke text (0) fonts will be used

**val**

`VAL` is active only when `Kywrd` = COMP, and determines the degree of compression applied to the exported file (see above).

- `-1` - Apply the default, optimum value for compression. This value represents the best combination of speed and compression. It varies according to the release level of the ZLIB compression package.
- `1-9` - Use this value to specify a specific compression level. 1 is the lowest compression level (fastest) and 9 is the highest compression level (slowest).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PNGR.html
