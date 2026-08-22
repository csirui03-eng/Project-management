---
apdl: "ALIST"
method: alist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.alist
generated: 2026-08-22
tags: [mapdl-command]
---

# ALIST

PyMAPDL: `mapdl.alist(na1='', na2='', ninc='', lab='', **kwargs)`

Lists the defined areas.

## Parameters

**na1**, **na2**, **ninc**: List areas from `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL (default), `NA2` and `NINC` are ignored and all selected areas ( [[asel|ASEL]] ) are listed. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**lab**

Determines what type of listing is used (one of the following):

- `(blank)` - Prints information about all areas in the specified range.
- `HPT` - Prints information about only those areas that contain hard points.

## Notes

An attribute (TYPE, MAT, REAL, or ESYS) listed as a zero is unassigned; one listed as a positive value indicates that the attribute was assigned with the [[aatt|AATT]] command (and will not be reset to zero if the mesh is cleared); one listed as a negative value indicates that the attribute was assigned using the attribute pointer ( [[type|TYPE]], [[mat|MAT]], [[real|REAL]], or [[esys|ESYS]] ) that was active during meshing (and will be reset to zero if the mesh is cleared). A "-1" in the "nodes" column indicates that the area has been meshed but there are no interior nodes. The area size is listed only if an [[asum|ASUM]] command has been performed on the area.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ALIST.html
