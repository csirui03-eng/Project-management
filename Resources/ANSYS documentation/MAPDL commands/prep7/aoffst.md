---
apdl: "AOFFST"
method: aoffst
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.aoffst
generated: 2026-08-22
tags: [mapdl-command]
---

# AOFFST

PyMAPDL: `mapdl.aoffst(narea='', dist='', kinc='', **kwargs)`

Generates an area, offset from a given area.

## Parameters

**narea**: Area from which generated area is to be offset. If `NAREA` = ALL, offset from all selected areas ( [[asel|ASEL]] ). If `NAREA` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

**dist**: Distance normal to given area at which keypoints for generated area are to be located. Positive normal is determined from the right-hand-rule keypoint order.

**kinc**: Keypoint increment between areas. If zero, the lowest available keypoint numbers are assigned ( [[numstr|NUMSTR]] ).

## Notes

Generates an area (and its corresponding keypoints and lines) offset from a given area. The direction of the offset varies with the given area normal. End slopes of the generated lines remain the same as those of the given pattern. Area and line numbers are automatically assigned, beginning with the lowest available values ( [[numstr|NUMSTR]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AOFFST.html
