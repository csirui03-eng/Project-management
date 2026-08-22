---
apdl: "/AXLAB"
method: axlab
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.axlab
generated: 2026-08-22
tags: [mapdl-command]
---

# /AXLAB

PyMAPDL: `mapdl.axlab(axis='', lab='', **kwargs)`

Labels the X and Y axes on graph displays.

**Command default:**

Labels are determined by the program.

## Parameters

**axis**

Axis specifier:

- `X` - Apply label to X axis.
- `Y` - Apply label to Y axis.

**lab**: Axis label (user defined text up to 30 characters long). Leave blank to reestablish the default for `Axis` axis.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AXLAB.html
