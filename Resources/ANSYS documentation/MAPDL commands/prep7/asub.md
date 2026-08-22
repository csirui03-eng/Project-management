---
apdl: "ASUB"
method: asub
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.asub
generated: 2026-08-22
tags: [mapdl-command]
---

# ASUB

PyMAPDL: `mapdl.asub(na1='', p1='', p2='', p3='', p4='', **kwargs)`

Generates an area using the shape of an existing area.

## Parameters

**na1**: Existing area number whose shape is to be used. If `P1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

**p1**: Keypoint defining starting corner of area.

**p2**: Keypoint defining second corner of area.

**p3**: Keypoint defining third corner of area.

**p4**: Keypoint defining fourth corner of area (defaults to `P3` ).

## Notes

The new area will overlay the old area. Often used when the area to be subdivided consists of a complex shape that was not generated in a single coordinate system. Keypoints and any corresponding lines must lie on the existing area. Missing lines are generated to lie on the given area. The active coordinate system is ignored.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASUB.html
