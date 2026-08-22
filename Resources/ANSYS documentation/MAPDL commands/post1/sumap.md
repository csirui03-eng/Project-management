---
apdl: "SUMAP"
method: sumap
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.sumap
generated: 2026-08-22
tags: [mapdl-command]
---

# SUMAP

PyMAPDL: `mapdl.sumap(rsetname='', item='', comp='', **kwargs)`

Map results onto selected surface(s).

## Parameters

**rsetname**: Eight-character name for the result being mapped.

**item**

Label identifying the item.

Valid item labels are defined via [[plnsol|PLNSOL]]. Some items also require a component label.

If `Item` = CLEAR, the specified result set is deleted from all selected surfaces

**comp**: Component label of item (if required).

## Notes

The **SUMAP** command maps results in the current coordinate system ( [[rsys|RSYS]] ) using the selected set of elements.

The command interpolates and stores the results data on to each of the selected surfaces.

**SUMAP**,ALL,CLEAR deletes all results sets from all selected surfaces.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUMAP.html
