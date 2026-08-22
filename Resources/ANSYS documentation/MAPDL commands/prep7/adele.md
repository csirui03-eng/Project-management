---
apdl: "ADELE"
method: adele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.adele
generated: 2026-08-22
tags: [mapdl-command]
---

# ADELE

PyMAPDL: `mapdl.adele(na1='', na2='', ninc='', kswp='', **kwargs)`

Deletes unmeshed areas.

## Parameters

**na1**, **na2**, **ninc**: Delete areas from `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL, `NA2` and `NINC` are ignored and all selected areas ( [[asel|ASEL]] ) are deleted. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**kswp**

Specifies whether keypoints and lines are also to be deleted:

- `0` - Delete areas only (default).
- `1` - Delete areas, as well as keypoints and lines attached to specified areas but not shared by other areas.

## Notes

An area attached to a volume cannot be deleted unless the volume is first deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADELE.html
