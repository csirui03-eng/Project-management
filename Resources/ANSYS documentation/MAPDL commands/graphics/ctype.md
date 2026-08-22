---
apdl: "/CTYPE"
method: ctype
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.ctype
generated: 2026-08-22
tags: [mapdl-command]
---

# /CTYPE

PyMAPDL: `mapdl.ctype(key='', dotd='', dots='', dshp='', tlen='', **kwargs)`

Specifies the type of contour display.

**Command default:**

Standard contour display.

## Parameters

**key**

Type of display:

- `0` - Standard contour display.
- `1` - Isosurface display.
- `2` - Particle gradient display.
- `3` - Gradient triad display.

**dotd**: Maximum dot density for particle gradient display ( `KEY` = 2). Density is expressed as dots per screen width (defaults to 30).

**dots**: Dot size for particle gradient display ( `KEY` = 2). Size is expressed as a fraction of the screen width (defaults to 0.0 (single dot width)).

**dshp**

Spherical dot shape precision for particle gradient display ( `KEY` = 2). (3D options are supported only on 3D devices):

- `0` - Flat 2D circular dot.
- `1` - Flat-sided 3D polyhedron.
- `n` - 3D sphere with `n` (\>1) polygon divisions per 90° of radius.

**tlen**: Maximum length of triads for gradient triad display ( `KEY` = 3). Value is expressed as a fraction of the screen width (defaults to 0.067).

## Notes

Use **/CTYPE**,STAT to display the current settings. Only the standard contour display ( **/CTYPE**,0) and the isosurface contour display ( **/CTYPE**,1) are supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CTYPE.html
