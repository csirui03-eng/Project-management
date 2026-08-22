---
apdl: "/CVAL"
method: cval
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.cval
generated: 2026-08-22
tags: [mapdl-command]
---

# /CVAL

PyMAPDL: `mapdl.cval(wn='', v1='', v2='', v3='', v4='', v5='', v6='', v7='', v8='', **kwargs)`

Specifies nonuniform contour values on stress displays.

**Command default:**

Nine contour values uniformly spaced between the extreme values.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**, **v7**, **v8**: Up to 8 contour values may be specified (in ascending order). The 0.0 value (if any) must not be the last value specified. If no values are specified, all contour specifications are erased and contours are automatically calculated.

## Notes

This command is similar to the [[contour|/CONTOUR]] command. With **/CVAL**, however, you define the upper level of each contour band instead of having the contours uniformly distributed over the range. The minimum value (including a zero value for the first band) for a contour band cannot be specified. If you use both [[contour|/CONTOUR]] and **/CVAL**, the last command issued takes precedence.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CVAL.html
