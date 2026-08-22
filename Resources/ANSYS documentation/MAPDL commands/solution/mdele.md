---
apdl: "MDELE"
method: mdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.master_dof.MasterDof.mdele
generated: 2026-08-22
tags: [mapdl-command]
---

# MDELE

PyMAPDL: `mapdl.mdele(node='', lab1='', nend='', ninc='', lab2='', lab3='', lab4='', lab5='', lab6='', support='', **kwargs)`

Deletes master degrees of freedom.

## Parameters

**node**: Delete master degrees of freedom in the `Lab1` direction ( [[m|M]] ) from `NODE` to `NEND` (defaults to `NODE` ) in steps of `NINC` (defaults to 1). If `NODE` = ALL, `NEND` and `NINC` are ignored and masters for all selected nodes ( [[nsel|NSEL]] ) are deleted. If `Lab1` = ALL, all label directions will be deleted. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**lab1**: Delete masters in these additional directions.

**nend**, **ninc**: Delete master degrees of freedom in the `Lab1` direction ( [[m|M]] ) from `NODE` to `NEND` (defaults to `NODE` ) in steps of `NINC` (defaults to 1). If `NODE` = ALL, `NEND` and `NINC` are ignored and masters for all selected nodes ( [[nsel|NSEL]] ) are deleted. If `Lab1` = ALL, all label directions will be deleted. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**lab2**, **lab3**, **lab4**, **lab5**, **lab6**: Delete masters in these additional directions.

**support**

Pseudo-constraints key for the free-interface ( [[cmsopt|CMSOPT]],FREE) and residual-flexible free- interface ( [[cmsopt|CMSOPT]],RFFB) CMS method analyses:

OFF - delete selected master degrees of freedom and any pseudo-constraints applied on them with SUPPORT = ON in the [[m|M]] command (default).

ON - only delete any pseudo-constraints applied on selected master degrees of freedom.

## Notes

Deletes master degrees of freedom. If used in SOLUTION, this command is valid only within the first load step.

The `SUPPORT` argument is ignored for the fixed-interface CMS method analysis ( [[cmsopt|CMSOPT]],FIX).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MDELE.html
