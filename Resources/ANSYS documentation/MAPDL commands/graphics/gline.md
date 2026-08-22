---
apdl: "/GLINE"
method: gline
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.gline
generated: 2026-08-22
tags: [mapdl-command]
---

# /GLINE

PyMAPDL: `mapdl.gline(wn='', style='', **kwargs)`

Specifies the element outline style.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**style**

Outline key:

- `0` - Solid element outlines (default)
- `1` - Dashed element outlines
- `-1` - No element outlines

## Notes

Determines the element outline style. Often used when node numbers are displayed to prevent element lin es from overwriting node numbers.

Unless you are using an OpenGL or Starbase driver, the dashed element outline option ( **/GLINE**, `WN`,1) is not available in the following situations:

- Z-buffered displays ( [[slashtype|/TYPE]], `WN`,6).
- Capped Z-buffered displays ( [[slashtype|/TYPE]], `WN`,7).
- Qslice Z-buffered displays ( [[slashtype|/TYPE]], `WN`,8).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GLINE.html
