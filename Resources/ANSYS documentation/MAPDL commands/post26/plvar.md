---
apdl: "PLVAR"
method: plvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.display.Display.plvar
generated: 2026-08-22
tags: [mapdl-command]
---

# PLVAR

PyMAPDL: `mapdl.plvar(nvar1='', nvar2='', nvar3='', nvar4='', nvar5='', nvar6='', nvar7='', nvar8='', nvar9='', nvar10='', **kwargs)`

Displays up to ten variables in the form of a graph.

## Parameters

**nvar1**, **nvar2**, **nvar3**, **nvar4**, **nvar5**, **nvar6**, **nvar7**, **nvar8**, **nvar9**, **nvar10**: Variables to be displayed, defined either by the reference number or a unique thirty-two character name. If duplicate names are used the command will plot the data for the lowest- numbered variable with that name.

## Notes

Variables are displayed vs. variable `N` on the [[xvar|XVAR]] command. The string value will be a predefined, unique name. For complex variables, the amplitude is displayed by default ( [[plcplx|PLCPLX]] ). Each **PLVAR** command produces a new frame. See the [[grtyp|/GRTYP]] command for displaying multiple variables in a single frame with separate Y-axes.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLVAR.html
