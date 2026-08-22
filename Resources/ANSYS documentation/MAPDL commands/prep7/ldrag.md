---
apdl: "LDRAG"
method: ldrag
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ldrag
generated: 2026-08-22
tags: [mapdl-command]
---

# LDRAG

PyMAPDL: `mapdl.ldrag(nk1='', nk2='', nk3='', nk4='', nk5='', nk6='', nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', **kwargs)`

Generates lines by sweeping a keypoint pattern along path.

## Parameters

**nk1**, **nk2**, **nk3**, **nk4**, **nk5**, **nk6**: List of keypoints in the pattern to be dragged (6 maximum if using keyboard entry). If `NK1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). If `NK1` = ALL, all selected keypoints (except those that define the drag path) will be swept along the path. A component name may also be substituted for `NK1`.

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**: List of lines defining the path along which the pattern is to be dragged (6 maximum if using keyboard entry). Must be a continuous set of lines.

## Notes

Generates lines (and their corresponding keypoints) by sweeping a given keypoint pattern along a characteristic drag path. If the drag path consists of multiple lines, the drag direction is determined by the sequence in which the path lines are input ( `NL1`, `NL2`, etc.). If the drag path is a single line ( `NL1` ), the drag direction is from the keypoint on the drag line that is closest to the first keypoint of the given pattern to the other end of the drag line.

The magnitude of the vector between the keypoints of the given pattern and the first path keypoint remains constant for all generated keypoint patterns and the path keypoints. The direction of the vector relative to the path slope also remains constant so that patterns may be swept around curves. Keypoint and line numbers are automatically assigned (beginning with the lowest available values ( [[numstr|NUMSTR]] )). For best results, the entities to be dragged should be orthogonal to the start of the drag path. Drag operations that produce an error message may create some of the desired entities prior to terminating.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LDRAG.html
