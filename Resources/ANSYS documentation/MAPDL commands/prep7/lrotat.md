---
apdl: "LROTAT"
method: lrotat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lrotat
generated: 2026-08-22
tags: [mapdl-command]
---

# LROTAT

PyMAPDL: `mapdl.lrotat(nk1='', nk2='', nk3='', nk4='', nk5='', nk6='', pax1='', pax2='', arc='', nseg='', **kwargs)`

Generates circular lines by rotating a keypoint pattern about an axis.

## Parameters

**nk1**, **nk2**, **nk3**, **nk4**, **nk5**, **nk6**: List of keypoints in the pattern to be rotated (6 maximum if using keyboard entry). If `NK1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). If `NK1` = ALL, all selected keypoints (except `PAX1` and `PAX2` ) will define the pattern to be rotated. A component name may also be substituted for `NK1`.

**pax1**, **pax2**: Keypoints defining the axis about which the keypoint pattern is to be rotated.

**arc**: Arc length (in degrees). Positive follows right-hand rule about `PAX1` - `PAX2` vector. Defaults to 360.

**nseg**: Number of lines (8 maximum) around circumference. Defaults to minimum required for 90° (maximum) arcs, that is, 4 for 360°, 3 for 270°, etc.

## Notes

Generates circular lines (and their corresponding keypoints) by rotating a keypoint pattern about an axis. Keypoint patterns are generated at regular angular locations (based on a maximum spacing of 90°). Line patterns are generated at the keypoint patterns. Keypoint and line numbers are automatically assigned (beginning with the lowest available values ( [[numstr|NUMSTR]] )).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LROTAT.html
