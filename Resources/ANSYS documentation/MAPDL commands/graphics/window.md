---
apdl: "/WINDOW"
method: window
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.window
generated: 2026-08-22
tags: [mapdl-command]
---

# /WINDOW

PyMAPDL: `mapdl.window(wn='', xmin='', xmax='', ymin='', ymax='', ncopy='', **kwargs)`

Defines the window size on the screen.

## Parameters

**wn**: Window reference number (1 to 5). Defaults to 1. This number, or ALL (for all active windows), may be used on other commands.

**xmin**, **xmax**, **ymin**, **ymax**: Screen coordinates defining window size. Screen coordinates are measured as -1.0 to 1.67 with the origin at the screen center. For example, (-1,1.67,-1,1) is full screen, (-1,0,-1,0) is the left bottom quadrant. If `XMIN` = OFF, deactivate this previously defined window; if ON, reactivate this previously defined window. If FULL, LEFT, RIGH, TOP, BOT, LTOP, LBOT, RTOP, RBOT, form full, half, or quarter window. If SQUA, form largest square window within the current graphics area. If DELE, delete this window (cannot be reactivated with ON).

**ncopy**: Copies the current specifications from window `NCOPY` (1 to 5) to this window. If `NCOPY` = 0 (or blank), no specifications are copied.

## Notes

Defines the window size on the screen. Windows may occupy a separate section of the screen or they may overlap. Requested displays are formed in all windows according to the selected window specifications.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WINDOW.html
