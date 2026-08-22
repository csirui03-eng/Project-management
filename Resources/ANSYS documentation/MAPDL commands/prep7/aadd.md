---
apdl: "AADD"
method: aadd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.aadd
generated: 2026-08-22
tags: [mapdl-command]
---

# AADD

PyMAPDL: `mapdl.aadd(na1='', na2='', na3='', na4='', na5='', na6='', na7='', na8='', na9='', **kwargs)`

Adds separate areas to create a single area.

## Parameters

**na1**, **na2**, **na3**, **na4**, **na5**, **na6**, **na7**, **na8**, **na9**: Numbers of areas to be added. If `NA1` = ALL, add all selected areas and ignore `NA2` to `NA9`. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1`.

## Notes

The areas must be coplanar. The original areas (and their corresponding lines and keypoints) will be deleted by default. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated. Concatenated entities are not valid with this command.

## Examples

Generate two areas and combine them.

``` python
>>> a1 = mapdl.rectng(2.5, 3.5, 0, 10)
>>> a2 = mapdl.cyl4(0, 10, 2.5, 0, 3.5, 90)
>>> a_comb = mapdl.aadd(a1, a2)
>>> a_comb
3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AADD.html
