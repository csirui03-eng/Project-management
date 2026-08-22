---
apdl: "KWPLAN"
method: kwplan
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.kwplan
generated: 2026-08-22
tags: [mapdl-command]
---

# KWPLAN

PyMAPDL: `mapdl.kwplan(wn='', korig='', kxax='', kplan='', **kwargs)`

Defines the working plane using three keypoints.

## Parameters

**wn**: Window number whose viewing direction will be modified to be normal to the working plane (defaults to 1). If `WN` is a negative value, the viewing direction will not be modified. If fewer than three points are used, the viewing direction of window `WN` will be used instead to define the normal to the working plane.

**korig**: Keypoint number defining the origin of the working plane coordinate system. If `KORIG` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**kxax**: Keypoint number defining the x-axis orientation (defaults to the x-axis being parallel to the global X-axis; or if the normal to the working plane is parallel to the global X-axis, then defaults to being parallel to the global Y-axis).

**kplan**: Keypoint number defining the working plane (the normal defaults to the present display view ( [[view|/VIEW]] ) of window `WN` ).

## Notes

Defines a working plane to assist in picking operations using three keypoints as an alternate to the [[wplane|WPLANE]] command. The three keypoints also define the working plane coordinate system. A minimum of one keypoint (at the working plane origin) is required. Immediate mode may also be active. See [[wpstyl|WPSTYL]] command to set the style of working plane display.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KWPLAN.html
