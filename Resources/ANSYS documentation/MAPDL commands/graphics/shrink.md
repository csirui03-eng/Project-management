---
apdl: "/SHRINK"
method: shrink
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.scaling.Scaling.shrink
generated: 2026-08-22
tags: [mapdl-command]
---

# /SHRINK

PyMAPDL: `mapdl.shrink(ratio='', **kwargs)`

Shrinks elements, lines, areas, and volumes for display clarity.

## Parameters

**ratio**: Shrinkage ratio (input as a decimal (0.0 to 0.5)). Defaults to 0.0 (no shrinkage). Values greater than 0.5 default to 0.1 (10% shrinkage).

## Notes

Shrinks the elements, lines, areas, and volumes so that adjacent entities are separated for clarity. Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

If only the common lines of non-coplanar faces are drawn (as per the [[edge|/EDGE]] command), then this command is ignored.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SHRINK.html
