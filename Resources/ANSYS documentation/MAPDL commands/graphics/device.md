---
apdl: "/DEVICE"
method: device
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.device
generated: 2026-08-22
tags: [mapdl-command]
---

# /DEVICE

PyMAPDL: `mapdl.device(label='', key='', **kwargs)`

Controls graphics device options.

**Command default:**

Vector mode off (that is, raster mode); dithering on.

## Parameters

**label**

Device function label:

- `BBOX` - Bounding box mode. For PowerGraphics plots involving elements with [[show|/SHOW]],x11 and [[show|/SHOW]],win32, Mechanical APDL generally displays dynamic rotations faster. If KEY = 1 (ON), then a bounding box (not the elements) encompassing the model is displayed and rotated, rather than the element outlines (ON is default in preprocessing). When KEY = 0 (OFF), then dynamic rotations may be slower (Mechanical APDL redraws the element outlines) for plots involving elements with [[show|/SHOW]],x11 and [[show|/SHOW]],win32. OFF is default in postprocessing. This command is ignored if [[edge|/EDGE]],WN,1 is set for any WN. This is ignored in POST1 and SOLUTION plots.

  For any PowerGraphics plots involving elements, regardless of [[show|/SHOW]] settings, plots will generally be displayed faster.

- `VECTOR` - Vector mode. In vector mode, areas, volumes, elements, and postprocessing display geometries are shown as outlines (wireframes). When vector mode is off (default), these entities are shown filled with color.

- `DITHER` - When dithering is turned on (default), color intensity transitions are smoothed. This selection a

  applies only to smooth-shaded images, that is, Z-buffered ( [[slashtype|/TYPE]] ), or raster plots with Gouraud or Phong shading ( [[shade|/SHADE]] ).

- `ANIM` - Select the animation type used on 2D devices on the PC platform. A `KEY` value of BMP (or 0) sets animation mode to the Mechanical APDL animation controller (default). A `KEY` value of AVI (or 2) sets animation mode to AVI movie player file.

- `FONT` - Font selection for the Mechanical APDL graphics window. When `Label` = FONT, the command format is: **/DEVICE**,FONT, `KEY`, `Val1`, `Val2`, `Val3`, `Val4`, `Val5`, `Val6` where `KEY` determines the type of font being controlled, and values 1 through 6 control various font parameters. These values are device specific; using the same command input file ( [[input|/INPUT]] ) on different machines may yield different results.. The following `KEY` values determine the font information that will be supplied to the appropriate driver (for example, Postscript, X11, Win32, JPEG,...):

  - `KEY = 1` - The command controls the LEGEND (documentation column) font.
  - `KEY = 2` - The command controls the ENTITY (node and keypoint number) font.
  - `KEY = 3` - The command controls the ANNOTATION/GRAPH font.

  Linux: Values 1 through 4 are used to find a match in the X11 database of font strings. Values 1, 2, and 3 are character strings; value 4 is a nonzero integer:

  - `Val1` - Family name (for example, Courier). If `Val1` = MENU, all other values are ignored and a font selection menu appears (GUI must be active).
  - `Val2` - Weight (for example, medium)
  - `Val3` - Slant (for example, r)
  - `Val4` - Pixel size (for example, 14). Note that this value does no affect the annotation fonts ( `KEY` = 3). Use the [[tspec|/TSPEC]] command for annotation font size.
  - `Val5` - unused
  - `Val6` - unused

  PC: The values are encoded in a PC logical font structure. Value 1 is a character string, and the remaining values are integers:

  - `Val1` - Family name (for example, Courier2New) Substitute an asterisk (2) for any blank character that appears in a family name. If `Val1` = MENU, all other values are ignored and a font selection menu appears (GUI must be active). When this value is blank, Mechanical APDL uses the first available resource it finds.
  - `Val2` - Weight (0 - 1000)
  - `Val3` - Orientation (in tenths of a degree)
  - `Val4` - Height (in logical units)
  - `Val5` - Width (in logical units)
  - `Val6` - Italics (0 = OFF, 1 = ON)

- `TEXT` - Text size specification for the Mechanical APDL graphics window. Using this label with the **/DEVICE** command requires the following form: **/DEVICE**,TEXT, `KEY`, `PERCENT`. `KEY` = 1 for LEGEND fonts; `KEY` = 2 for ENTITY fonts. `PERCENT` specifies the new text size as a percent of the default text size. If `PERCENT` = 100, the new text size is precisely the default size. If `PERCENT` = 200, the new text size is twice the default text size.

**key**

Control key:

- `OFF or 0` - Turns specified function off.
- `ON or 1` - Turns specified function on or designates the LEGEND font.
- `2` - Designates the ENTITY font.
- `3` - Designates the ANNOTATION/GRAPH font.

## Notes

This command is valid in any processor.

The **/DEVICE**,BBOX command is ignored in POST1 and SOLUTION plots. Also, the elements are displayed and rotated if you use **/DEVICE**,BBOX,ON and [[edge|/EDGE]],WN,1,ANGLE (effectively ignoring the BBOX option).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DEVICE.html
