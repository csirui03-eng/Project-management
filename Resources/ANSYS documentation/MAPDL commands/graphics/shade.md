---
apdl: "/SHADE"
method: shade
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.shade
generated: 2026-08-22
tags: [mapdl-command]
---

# /SHADE

PyMAPDL: `mapdl.shade(wn='', type_='', **kwargs)`

Defines the type of surface shading used with Z-buffering.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**type_**

Shading type:

- `FACET or 0` - Facet shading (one color per area face).
- `GOURAUD or 1` - Gouraud smooth shading (smooth variation of color based on interpolated vertex colors) (default).
- `PHONG or 2` - Phong smooth shading (smooth variation of color based on interpolated vertex normals).

## Notes

Defines the type of surface shading used on area, volume, and PowerGraphics ( [[graphics|/GRAPHICS]],POWER) displays when software Z-buffering is enabled ( [[slashtype|/TYPE]] ). This command is only functional for 2D display devices.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SHADE.html
