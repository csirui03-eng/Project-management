---
apdl: "/GMARKER"
method: gmarker
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.gmarker
generated: 2026-08-22
tags: [mapdl-command]
---

# /GMARKER

PyMAPDL: `mapdl.gmarker(curve='', key='', incr='', **kwargs)`

Specifies the curve marking style.

## Parameters

**curve**: Curve number markers will be applied on (integer value between 1 and 10).

**key**

Marker key:

- `0` - No markers will be applied (default).
- `1` - TRIANGLES will be applied.
- `2` - SQUARES will be applied.
- `3` - DIAMONDS will be applied.
- `4` - CROSSES will be applied.

**incr**: Determines the curve marking frequency. (a whole number value between 1 and 255). If `INCR` = 1, markers are displayed at every data point on the curve. If `INCR` = 2 then markers are displayed at every second data point. If `INCR` = 3 then they are displayed at every third data point.

## Notes

The user-specified markers will not be drawn when the area under the curve is color-filled ( [[gropt|/GROPT]], FILL).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GMARKER.html
