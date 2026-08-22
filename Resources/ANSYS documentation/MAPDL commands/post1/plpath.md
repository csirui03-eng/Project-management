---
apdl: "PLPATH"
method: plpath
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.plpath
generated: 2026-08-22
tags: [mapdl-command]
---

# PLPATH

PyMAPDL: `mapdl.plpath(lab1='', lab2='', lab3='', lab4='', lab5='', lab6='', **kwargs)`

Displays path items on a graph.

## Parameters

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Labels identifying the path items to be displayed. Up to six items may be drawn per frame. Predefined path geometry items XG, YG, ZG, and S ( [[pdef|PDEF]] ) may also be displayed.

## Notes

The path must have been defined by the [[path|PATH]] and [[ppath|PPATH]] commands. Path items and their labels must have been defined with the [[pdef|PDEF]], [[pvect|PVECT]], [[pcalc|PCALC]], [[pdot|PDOT]], [[pcross|PCROSS]], or [[plnear|PLNEAR]] commands. Path items may also be printed with the [[prpath|PRPATH]] command. Graph scaling may be controlled with the [[xrange|/XRANGE]], [[yrange|/YRANGE]], and [[prange|PRANGE]] commands. You need to type all six characters to issue this command.

Fore more information, see [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLPATH.html
