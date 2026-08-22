---
apdl: "AROTAT"
method: arotat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.arotat
generated: 2026-08-22
tags: [mapdl-command]
---

# AROTAT

PyMAPDL: `mapdl.arotat(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', pax1='', pax2='', arc='', nseg='', **kwargs)`

Generates cylindrical areas by rotating a line pattern about an axis.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**: List of lines in the pattern to be rotated (6 maximum if using keyboard entry of `NL1` to `NL6` ). The lines must lie in the plane of the axis of rotation. If `NL1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). If `NL1` = ALL, all selected lines will define the pattern to be rotated. A component name may also be substituted for `NL1`.

**pax1**, **pax2**: Keypoints defining the axis about which the line pattern is to be rotated.

**arc**: Arc length (in degrees). Positive follows right-hand rule about `PAX1` - `PAX2` vector. Defaults to 360°.

**nseg**: Number of areas (8 maximum) around circumference. Defaults to minimum number required for 90° -maximum arcs, that is, 4 for 360°, 3 for 270°, etc.

## Notes

Generates cylindrical areas (and their corresponding keypoints and lines) by rotating a line pattern (and its associated keypoint pattern) about an axis. Keypoint patterns are generated at regular angular locations, based on a maximum spacing of 90°. Line patterns are generated at the keypoint patterns. Arc lines are also generated to connect the keypoints circumferentially. Keypoint, line, and area numbers are automatically assigned, beginning with the lowest available values ( [[numstr|NUMSTR]] ). Adjacent lines use a common keypoint. Adjacent areas use a common line.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AROTAT.html
