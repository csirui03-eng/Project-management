---
apdl: "/GCMD"
method: gcmd
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gcmd
generated: 2026-08-22
tags: [mapdl-command]
---

# /GCMD

PyMAPDL: `mapdl.gcmd(wn='', lab1='', lab2='', lab3='', lab4='', lab5='', lab6='', lab7='', lab8='', lab9='', lab10='', lab11='', lab12='', **kwargs)`

Controls the type of element or graph display used for the [[gplot|GPLOT]] command.

## Parameters

**wn**: Window number (or ALL) to which this command applies (defaults to 1)

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**, **lab6**, **lab7**, **lab8**, **lab9**, **lab10**, **lab11**, **lab12**: Command labels (for example, [[plnsol|PLNSOL]],S,X)

## Notes

This command controls the type of element or graph display that appears when you issue the [[gplot|GPLOT]] command when the [[gtype|/GTYPE]],,(ELEM or GRPH) entity type is active. If you have multiple plotting windows enabled, you can also use **/GCMD** to select one window when you wish to edit its contents.

For related information, see the descriptions of the [[gplot|GPLOT]] and [[gtype|/GTYPE]] commands in this manual.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GCMD.html
