---
apdl: "/USER"
method: user
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.user
generated: 2026-08-22
tags: [mapdl-command]
---

# /USER

PyMAPDL: `mapdl.user(wn='', **kwargs)`

Conveniently resets [[focus|/FOCUS]] and [[dist|/DIST]] to USER.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

## Notes

Conveniently resets scale parameters to USER on the [[focus|/FOCUS]] and [[dist|/DIST]] commands. Scale parameters will be internally respecified to those used for the last display. Convenient when the last scale parameters were automatically calculated. User specified parameters hold until changed or removed ( [[auto|/AUTO]] ). Parameters may be reset on the individual commands after this command has been issued.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_USER.html
