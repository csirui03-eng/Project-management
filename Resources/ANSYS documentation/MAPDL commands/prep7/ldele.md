---
apdl: "LDELE"
method: ldele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ldele
generated: 2026-08-22
tags: [mapdl-command]
---

# LDELE

PyMAPDL: `mapdl.ldele(nl1='', nl2='', ninc='', kswp='', **kwargs)`

Deletes unmeshed lines.

## Parameters

**nl1**, **nl2**, **ninc**: Delete lines from `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and all selected lines ( [[lsel|LSEL]] ) are deleted. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

**kswp**

Specifies whether keypoints are also to be deleted:

- `0` - Delete lines only.
- `1` - Delete lines, as well as keypoints attached to lines but not attached to other lines.

## Notes

A line attached to an area cannot be deleted unless the area is first deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LDELE.html
