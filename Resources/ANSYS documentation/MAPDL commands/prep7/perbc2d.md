---
apdl: "PERBC2D"
method: perbc2d
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.perbc2d
generated: 2026-08-22
tags: [mapdl-command]
---

# PERBC2D

PyMAPDL: `mapdl.perbc2d(loc1='', loc2='', loctol='', r1='', r2='', tolr='', opt='', plnopt='', **kwargs)`

Generates periodic constraints for 2D planar magnetic field analyses.

## Parameters

**loc1**: Constant coordinate location of the first plane of nodes. For `PLNOPT` = 1 or 2, the constant coordinate location is the global Cartesian coordinate system ( [[csys|CSYS]],0) location in the X or Y direction respectively. For `PLNOPT` = 0, the location is the angle in the global cylindrical coordinate system ( [[csys|CSYS]],1).

**loc2**: Constant coordinate location of the second plane of nodes. For `PLNOPT` = 1 or 2, the constant coordinate location is the global Cartesian coordinate system ( [[csys|CSYS]],0) location in the X or Y direction respectively. For `PLNOPT` = 0, the location is the angle (in degrees) in the global cylindrical coordinate system ( [[csys|CSYS]],1).

**loctol**: Tolerance on the constant coordinate location for node selection. Defaults to.00001 for `PLNOPT` = 1 or 2 and.001 degrees for `PLNOPT` = 0.

**r1**: Minimum coordinate location along the second plane of nodes. For `PLNOPT` = 1 or 2, the coordinate location is the global Cartesian coordinate system location in the Y or X direction respectively. For `PLNOPT` = 0, the coordinate location is the radial coordinate value in the global cylindrical coordinate system. Periodic conditions are not applied to nodes at this location.

**r2**: Maximum coordinate location along the second plane of nodes. For `PLNOPT` = 1 or 2, the coordinate location is the global Cartesian coordinate system location in the Y or X direction respectively. For `PLNOPT` = 0, the coordinate location is the radial coordinate value in the global cylindrical coordinate system. Periodic conditions are not applied to nodes at this location.

**tolr**: Tolerance dimension on node selection along the plane of nodes. Defaults to.00001.

**opt**

Periodic option:

- `0` - Odd symmetry (default). Apply constraint equations such that AZ(i) = -AZ(j).
- `1` - Even symmetry. Apply node coupling such that AZ(i) = AZ(j).

**plnopt**

Symmetry plane option:

- `0` - Planes of constant angle in the global cylindrical coordinate system ( [[csys|CSYS]],1).
- `1` - Planes parallel to the global Cartesian X axis ( [[csys|CSYS]],0).
- `2` - Planes parallel to the global Cartesian Y axis ( [[csys|CSYS]],0).

## Notes

**PERBC2D** invokes a Mechanical APDL macro which generates periodic boundary condition constraints for 2D planar magnetic field analysis.

The macro is restricted to node pairs sharing common coordinate values along symmetry planes separated by a constant coordinate value. Planes (or lines) must lie at either constant angles ( `PLNOPT` = 0), constant X values ( `PLNOPT` = 1), or constant Y values ( `PLNOPT` = 2).

The macro applies constraint equations ( `OPT` = 0, odd symmetry) or node coupling ( `OPT` = 1, even symmetry) to each node pair sharing a common coordinate value along the symmetry planes. By default, periodic conditions are not applied at the first and last node pairs on the symmetry planes unless the input location values, R1 and R2, are adjusted to be less than or greater than the actual node coordinate values.

Nodes are selected for application of constraints via [[nsel|NSEL]], with tolerances on the constant coordinate location ( `LOCTOL` ) and the coordinate location along the plane (RTOL).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PERBC2D.html
