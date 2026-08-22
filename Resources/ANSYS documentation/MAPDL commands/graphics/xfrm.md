---
apdl: "/XFRM"
method: xfrm
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.xfrm
generated: 2026-08-22
tags: [mapdl-command]
---

# /XFRM

PyMAPDL: `mapdl.xfrm(lab='', x1='', y1='', z1='', x2='', y2='', z2='', **kwargs)`

Controls the centroid or the axis of dynamic rotation.

**Command default:**

Issuing **/XFRM**, with no `LAB` defined sets the center of rotation at the focal point specified by the [[focus|/FOCUS]] command.

## Parameters

**lab**

The location or entity (centroid) used to define the center or axis of rotation.

- `NODE` - If NODE is chosen for the center of rotation, the node number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two nodes between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `ELEMENT` - If ELEMENT is chosen for the center of rotation, the element number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two elements between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `KP` - If KP is chosen for the center of rotation, the keypoint number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two keypoints between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `LINE` - If LINE is chosen for the center of rotation, the line number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two lines between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `AREA` - If AREA is chosen for the center of rotation, the area number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two areas between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `VOLUME` - If VOLUME is chosen for the center of rotation, the volume number will be `X1`. If the rotation is to be about an axis, then `X1` and `Y1` define the two volumes between which a line is drawn to determine the axis. The remaining arguments are ignored.
- `XYZ` - If XYZ is chosen for the center of rotation, the location of that center is determined by the coordinates `X1`, `Y1`, `Z1`. If values are specified for `X2`, `Y2`, `Z2`, then the axis of rotation will be about the line between those two points.
- `OFF` - If `LAB` = OFF, DEFAULT, FOCUS or if no value is specified, then the center of rotation is set at the FOCUS point, as defined by the [[focus|/FOCUS]] command.

**x1**: The entity number or X coordinate for the center of rotation.

**y1**: The entity number or Y coordinate for the center of rotation.

**z1**: The Z coordinate for the center of rotation.

**x2**: The X coordinate for the axis of rotation.

**y2**: The Y coordinate for the axis of rotation.

**z2**: The Z coordinate for the axis of rotation.

## Notes

The **/XFRM** command is active only when the cumulative rotation key is specified ON for the [[angle|/ANGLE]] command ( `KINCR` = 1). This command affects dynamic manipulations only.

For center rotation, the middle mouse button will rotate the model about the screen Z axis and the right mouse button will rotate the model about the screen X and Y axis.

For rotation about an axis, the middle mouse button will rotate the model about the defined axis of rotation and the right mouse button will be deactivated.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XFRM.html
