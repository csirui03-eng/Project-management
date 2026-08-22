---
apdl: "ADRAG"
method: adrag
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.adrag
generated: 2026-08-22
tags: [mapdl-command]
---

# ADRAG

PyMAPDL: `mapdl.adrag(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nlp1='', nlp2='', nlp3='', nlp4='', nlp5='', nlp6='', **kwargs)`

Generates areas by dragging a line pattern along a path.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**: List of lines in the pattern to be dragged (6 maximum if using keyboard entry). Lines should form a continuous pattern (no more than two lines connected to any one keypoint. If `NL1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). If `NL1` = ALL, all selected lines (except those that define the drag path) will be swept along the path. A component name may also be substituted for `NL1`.

**nlp1**, **nlp2**, **nlp3**, **nlp4**, **nlp5**, **nlp6**: List of lines defining the path along which the pattern is to be dragged (6 maximum if using keyboard entry). Must be a continuous set of lines.

## Notes

Generates areas (and their corresponding keypoints and lines) by sweeping a given line pattern along a characteristic drag path. If the drag path consists of multiple lines, the drag direction is determined by the sequence in which the path lines are input ( `NLP1`, `NLP2`, etc.). If the drag path is a single line ( `NLP1` ), the drag direction is from the keypoint on the drag line that is closest to the first keypoint of the given line pattern to the other end of the drag line.

The magnitude of the vector between the keypoints of the given pattern and the first path keypoint remains constant for all generated keypoint patterns and the path keypoints. The direction of the vector relative to the path slope also remains constant so that patterns may be swept around curves.

Keypoint, line, and area numbers are automatically assigned, beginning with the lowest available values ( [[numstr|NUMSTR]] ). Adjacent lines use a common keypoint. Adjacent areas use a common line. For best results, the entities to be dragged should be orthogonal to the start of the drag path. Drag operations that produce an error message may create some of the desired entities prior to terminating.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADRAG.html
