---
apdl: "IMMED"
method: immed
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.immed
generated: 2026-08-22
tags: [mapdl-command]
---

# IMMED

PyMAPDL: `mapdl.immed(key='', **kwargs)`

Allows immediate display of a model as it is generated.

## Parameters

**key**

Immediate mode key:

- `0` - Display only upon request, that is, no immediate display (default with the GUI off ).
- `1` - Display immediately as model is generated (default with the GUI on ).

## Notes

The command enables you to control whether or not the model is displayed immediately as it is generated in an interactive session. Available only during an interactive session at a graphics display terminal. A valid graphics device name must first be specified ( [[show|/SHOW]] ).

By default in the GUI, your model is immediately displayed in the Graphics window as you create new entities (such as areas, keypoints, nodes, elements, local coordinate systems, boundary conditions, etc.), referred to as immediate mode graphics.

Symbols (such as boundary conditions, local coordinate system triads, etc.) appear immediately and are present on subsequent displays unless you disable the appropriate symbol (via the GUI plot controls function or the appropriate graphics-specification command).

An immediate image is also scaled automatically to fit within the Graphics window. The new scaling is usually apparent on the automatic replot associated with immediate mode. To suppress automatic replot, issue [[uis|/UIS]],REPLOT,0. (With automatic replot suppressed, the immediate image may not always be scaled correctly.)

An immediate display in progress should not be aborted with the usual system "break" feature (or else the Mechanical APDL session itself terminates). When you run Mechanical APDL interactively without using the GUI, immediate mode is off by default.

This command is valid only in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IMMED.html
