---
apdl: "ELIST"
method: elist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.elist
generated: 2026-08-22
tags: [mapdl-command]
---

# ELIST

PyMAPDL: `mapdl.elist(iel1='', iel2='', inc='', nnkey='', rkey='', **kwargs)`

Lists the elements and their attributes.

## Parameters

**iel1**, **iel2**, **inc**: Lists elements from `IEL1` to `IEL2` (defaults to `IEL1` ) in steps of `INC` (defaults to 1). If `IEL1` = ALL (default), `IEL2` and `INC` are ignored and all selected elements ( [[esel|ESEL]] ) are listed. If `IEL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `IEL1` ( `IEL2` and `INC` are ignored).

**nnkey**

Node listing key:

- `0` - List attribute references and nodes.
- `1` - List attribute references but not nodes.

**rkey**

Real constant listing key:

- `0` - Do not show real constants for each element.
- `1` - Show real constants for each element. This includes default values chosen for the element.

## Notes

Lists the elements with their nodes and attributes (MAT, TYPE, REAL, ESYS, SECNUM, PART). See also the [[laylist|LAYLIST]] command for listing layered elements.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ELIST.html
