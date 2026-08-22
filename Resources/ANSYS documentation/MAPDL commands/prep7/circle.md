---
apdl: "CIRCLE"
method: circle
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.circle
generated: 2026-08-22
tags: [mapdl-command]
---

# CIRCLE

PyMAPDL: `mapdl.circle(pcent='', rad='', paxis='', pzero='', arc='', nseg='', **kwargs)`

Generates circular arc lines.

## Parameters

**pcent**: Keypoint defining the center of the circle (in the plane of the circle). If `PCENT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**rad**: Radius of the circle. If `RAD` is blank and `PCENT` = P, the radius is the distance from `PCENT` to `PZERO`.

**paxis**: Keypoint defining axis of circle (along with `PCENT` ). If `PCENT` = P and `PAXIS` is omitted, the axis is normal to the working plane.

**pzero**: Keypoint defining the plane normal to circle (along with `PCENT` and `PAXIS` ) and the zero degree location. Need not be in the plane of the circle. This value is not required if `PAXIS` is defined along the Y axis (that is, a circle in the XZ plane).

**arc**: Arc length (in degrees). Positive follows right-hand rule about `PCENT` - `PAXIS` vector. Defaults to 360°.

**nseg**: Number of lines around circumference (defaults to minimum required for 90°-maximum arcs, that is, 4 for 360°). Number of keypoints generated is `NSEG` for 360° or `NSEG` + 1 for less than 360°.

## Returns

`list`: List of lines of the circular arcs generated from this command.

## Notes

Generates circular arc lines (and their corresponding keypoints). Keypoints are generated at regular angular locations (based on a maximum spacing of 90°). Arc lines are generated connecting the keypoints. Keypoint and line numbers are automatically assigned, beginning with the lowest available values ( [[numstr|NUMSTR]] ). Adjacent lines use a common keypoint. Line shapes are generated as arcs, regardless of the active coordinate system. Line shapes are invariant with coordinate system after they are generated.

## Examples

Create a full circle containing four circular arcs. Circle centered at (0, 0, 0) and generated in the XY plane. Return the lines generated from the circle.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 0, 1)
>>> carc0 = mapdl.circle(k0, 1, k1)
>>> carc0
[1, 2, 3, 4]
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CIRCLE.html
