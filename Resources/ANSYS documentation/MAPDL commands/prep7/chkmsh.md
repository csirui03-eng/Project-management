---
apdl: "CHKMSH"
method: chkmsh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.chkmsh
generated: 2026-08-22
tags: [mapdl-command]
---

# CHKMSH

PyMAPDL: `mapdl.chkmsh(comp='', **kwargs)`

Checks area and volume entities for previous meshes.

## Parameters

**comp**: Name of component containing areas or volumes.

## Notes

**CHKMSH** invokes a predefined Mechanical APDL macro that checks areas and volumes to find out if they were previously meshed. This macro name will appear in the log file ( `Jobname.LOG` ) prior to area and volume meshing operations initiated through the GUI. This command is not intended to be typed in directly in a Mechanical APDL session (although it can be included in an input file for use via [[input|/INPUT]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CHKMSH.html
