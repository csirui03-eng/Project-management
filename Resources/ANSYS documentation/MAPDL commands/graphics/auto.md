---
apdl: "/AUTO"
method: auto
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.auto
generated: 2026-08-22
tags: [mapdl-command]
---

# /AUTO

PyMAPDL: `mapdl.auto(wn='', **kwargs)`

Resets the focus and distance specifications to "automatically calculated."

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

## Notes

Focus point and distance will be automatically calculated during next display. Settings may still be changed with the [[focus|/FOCUS]] and [[dist|/DIST]] commands after this command has been issued. See also the [[user|/USER]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AUTO.html
