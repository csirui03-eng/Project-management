---
apdl: "AFILLT"
method: afillt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.afillt
generated: 2026-08-22
tags: [mapdl-command]
---

# AFILLT

PyMAPDL: `mapdl.afillt(na1='', na2='', rad='', **kwargs)`

Generates a fillet at the intersection of two areas.

## Parameters

**na1**: Number of the first intersecting area. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

**na2**: Number of the second intersecting area.

**rad**: Radius of fillet to be generated.

## Notes

Generates an area of constant fillet radius at the intersection of two areas using a series of Boolean operations. Corresponding lines and keypoints are also generated. See [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. If areas do not initially intersect at a common line, use the [[aina|AINA]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AFILLT.html
