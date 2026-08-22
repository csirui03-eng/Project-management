---
apdl: "APTN"
method: aptn
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.aptn
generated: 2026-08-22
tags: [mapdl-command]
---

# APTN

PyMAPDL: `mapdl.aptn(na1='', na2='', na3='', na4='', na5='', na6='', na7='', na8='', na9='', **kwargs)`

Partitions areas.

## Parameters

**na1**, **na2**, **na3**, **na4**, **na5**, **na6**, **na7**, **na8**, **na9**: Numbers of areas to be operated on. If `NA1` = ALL, `NA2` to `NA9` are ignored and all selected areas are used. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may be substituted for `NA1`.

## Notes

Partitions areas that intersect. This command is similar to the combined functionality of the [[asba|ASBA]] and [[aovlap|AOVLAP]] commands. If the intersection of two or more areas is an area (that is, planar), new areas will be created with boundaries that conform to the area of intersection and to the boundaries of the non-intersecting portions of the input areas ( [[aovlap|AOVLAP]] ). If the intersection is a line (that is, not planar), the areas will be subtracted, or divided, along the line(s) of intersection ( [[asba|ASBA]] ). Both types of intersection can occur during a single **APTN** operation. Areas that do not intersect will not be modified. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_APTN.html
