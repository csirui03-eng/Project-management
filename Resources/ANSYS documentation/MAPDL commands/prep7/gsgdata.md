---
apdl: "GSGDATA"
method: gsgdata
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.gsgdata
generated: 2026-08-22
tags: [mapdl-command]
---

# GSGDATA

PyMAPDL: `mapdl.gsgdata(lfiber='', xref='', yref='', rotx0='', roty0='', **kwargs)`

Specifies the reference point and defines the geometry in the fiber direction for the generalized plane strain element option.

## Parameters

**lfiber**: Fiber length from the reference point. Defaults to 1.

**xref**: X coordinate of the reference point. Defaults to zero.

**yref**: Y coordinate of the reference point. Defaults to zero.

**rotx0**: Rotation of the ending plane about X in radians Defaults to zero.

**roty0**: Rotation of the ending plane about Y in radians Defaults to zero.

## Notes

The ending point is automatically determined from the starting (reference) point and the geometry inputs. All inputs are in the global Cartesian coordinate system. For more information about the generalized plane strain feature, see Generalized Plane Strain Option of Current-Technology Solid Elements in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSGDATA.html
