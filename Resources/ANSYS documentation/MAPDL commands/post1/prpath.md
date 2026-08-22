---
apdl: "PRPATH"
method: prpath
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.prpath
generated: 2026-08-22
tags: [mapdl-command]
---

# PRPATH

PyMAPDL: `mapdl.prpath(lab1='', lab2='', lab3='', lab4='', lab5='', lab6='', **kwargs)`

Prints path items along a geometry path.

## Parameters

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Labels identifying the path items to be printed. Up to six items may be printed at a time. Predefined path geometry items XG, YZ, ZG, and S ( [[pdef|PDEF]] ) may also be printed.

## Notes

Prints path items with respect to a geometry path (as defined by the [[path|PATH]] and [[ppath|PPATH]] commands). Path items and their labels must have been defined with the [[pdef|PDEF]], [[pvect|PVECT]], [[pcalc|PCALC]], [[pdot|PDOT]], [[pcross|PCROSS]], or [[prnear|PRNEAR]] commands. Path items may also be displayed with the [[plpath|PLPATH]] and [[plpagm|PLPAGM]] commands. See the [[prange|PRANGE]] command for range control of the path.

Fore more information, see [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRPATH.html
