---
apdl: "/SSCALE"
method: sscale
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.scaling.Scaling.sscale
generated: 2026-08-22
tags: [mapdl-command]
---

# /SSCALE

PyMAPDL: `mapdl.sscale(wn='', smult='', **kwargs)`

Sets the contour multiplier for topographic displays.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**smult**: Contour multiplier that factors in results based on the product of the multiplier and the result being plotted. Defaults to 0.0 (no topographic effects).

## Notes

Use this command to scale values to the geometry when the contours are shown elevated. For section displays ( [[slashtype|/TYPE]] ), the elevation is performed perpendicular to the section face.

Nonzero contour multipliers factoring in large results (stresses or displacements) can produce very large distortion, causing images to disappear. To bring a distorted image back into view, reduce the contour multiplier value.

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSCALE.html
