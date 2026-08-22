---
apdl: "/PSTATUS"
method: pstatus
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.pstatus
generated: 2026-08-22
tags: [mapdl-command]
---

# /PSTATUS

PyMAPDL: `mapdl.pstatus(wn='', **kwargs)`

Displays the global or window display specifications.

## Parameters

**wn**: Window number for status (defaults to global specifications).

## Notes

Displays the current global or window display specifications. Global display specifications are common to all windows (e.g. [[show|/SHOW]], etc.). Window display specifications are specific to one window (e.g. [[view|/VIEW]], [[slashtype|/TYPE]], etc.).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSTATUS.html
