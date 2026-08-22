---
apdl: "EDELE"
method: edele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.edele
generated: 2026-08-22
tags: [mapdl-command]
---

# EDELE

PyMAPDL: `mapdl.edele(iel1='', iel2='', inc='', **kwargs)`

Deletes selected elements from the model.

## Parameters

**iel1**, **iel2**, **inc**: Delete elements from `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `INC` (defaults to 1). If `IEL1` = ALL, `IEL2` and `INC` are ignored and all selected elements ( [[esel|ESEL]] ) are deleted. If `IEL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `INC` are ignored).

## Notes

Deleted elements are replaced by null or "blank" elements. Null elements are used only for retaining the element numbers so that the element numbering sequence for the rest of the model is not changed by deleting elements. Null elements may be removed (although this is not necessary) with the [[numcmp|NUMCMP]] command. If related element data (pressures, etc.) are also to be deleted, delete that data before deleting the elements. **EDELE** is for unattached elements only. You can use the **xCLEAR** family of commands to remove any attached elements from the database.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EDELE.html
