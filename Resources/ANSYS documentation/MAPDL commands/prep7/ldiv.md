---
apdl: "LDIV"
method: ldiv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ldiv
generated: 2026-08-22
tags: [mapdl-command]
---

# LDIV

PyMAPDL: `mapdl.ldiv(nl1='', ratio='', pdiv='', ndiv='', keep='', **kwargs)`

Divides a single line into two or more lines.

## Parameters

**nl1**: Number of the line to be divided. If negative, assume `P1` (see below) is the second keypoint of the line instead of the first for `RATIO`. If ALL, divide all selected lines ( [[lsel|LSEL]] ). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1`.

**ratio**: Ratio of line length `P1` - `PDIV` to line length `P1` - `P2`. Must be between 0.0 and 1.0. Input ignored if `NDIV` \> 2.

**pdiv**: Number to be assigned to keypoint generated at division location (defaults to lowest available keypoint number ( [[numstr|NUMSTR]] )). Input ignored if `NL1` = ALL or `NDIV` \> 2. If `PDIV` already exists and lies on line `NL1`, divide line at `PDIV` ( `RATIO` must also be 0.0). If `PDIV` already exists and does not lie on line `NL1`, `PDIV` is projected and moved to the nearest point on line `NL1` (if possible). `PDIV` cannot be attached to another line, area, or volume.

**ndiv**: The number of new lines to be generated from old line (defaults to 2).

**keep**

Specifies whether to keep the input entities:

- `0` - Modify old line to use new keypoints and slopes.
- `1` - Do not modify old line. New lines will overlay old line and have unique keypoints.

## Notes

Divides a single line `NL1` (defined from keypoint `P1` to keypoint `P2` ) into two or more lines. Line `NL1` becomes the new line beginning with keypoint `P1` and new lines are generated ending at keypoint `P2`. If the line is attached to an area, the area will also be updated. Line divisions are set to zero (use [[lesize|LESIZE]], etc. to modify).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LDIV.html
