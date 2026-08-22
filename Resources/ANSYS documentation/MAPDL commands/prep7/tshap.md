---
apdl: "TSHAP"
method: tshap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.tshap
generated: 2026-08-22
tags: [mapdl-command]
---

# TSHAP

PyMAPDL: `mapdl.tshap(shape='', **kwargs)`

Defines simple 2D and 3D geometric surfaces for target segment elements.

## Parameters

**shape**

Specifies the geometric shapes for target segment elements `TARGE169` and `TARGE170`.

- `LINE` - Straight line (2D, 3D) (Default for 2D)
- `PARA` - Parabola (2D, 3D)
- `ARC` - Clockwise arc (2D)
- `CARC` - Counterclockwise arc (2D)
- `CIRC` - Complete circle (2D)
- `TRIA` - Three-node triangle (3D) (Default for 3D)
- `TRI6` - Six-node triangle (3D)
- `QUAD` - Four-node quadrilateral (3D)
- `QUA8` - Eight-node quadrilateral (3D)
- `CYLI` - Cylinder (3D)
- `CONE` - Cone (3D)
- `SPHE` - Sphere (3D)
- `PILO` - Pilot node (2D, 3D)
- `POINT` - Point (rigid surface node) (2D, 3D)

## Notes

Use this command to specify the target segment shapes for the rigid target surface associated with surface-to-surface contact ( `TARGE169`, `CONTA172` (2D) and `TARGE170`, `CONTA174` (3D)), 3D beam-to-beam contact ( `TARGE170` and `CONTA177` ), and 3D line-to-surface contact ( `TARGE170` and `CONTA177` ). Once you issue **TSHAP**, all subsequent target elements generated via the direct element generation technique will have the same shape, until you issue **TSHAP** again with a different `Shape` value.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TSHAP.html
