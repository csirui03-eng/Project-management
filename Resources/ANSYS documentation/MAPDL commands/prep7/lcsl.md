---
apdl: "LCSL"
method: lcsl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lcsl
generated: 2026-08-22
tags: [mapdl-command]
---

# LCSL

PyMAPDL: `mapdl.lcsl(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nl7='', nl8='', nl9='', **kwargs)`

Divides intersecting lines at their point(s) of intersection.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**, **nl7**, **nl8**, **nl9**: Numbers of lines to be intersected. If `NL1` = ALL, `NL2` to `NL9` are ignored and the intersection of all selected lines is found. If `NL1` = P, use graphical picking to specify lines ( `NL2` to `NL9` are ignored).

## Notes

Divides intersecting (classifies) lines at their point(s) of intersection. The original lines (and their corresponding keypoint(s)) will be deleted by default. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCSL.html
