---
apdl: "AOVLAP"
method: aovlap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.aovlap
generated: 2026-08-22
tags: [mapdl-command]
---

# AOVLAP

PyMAPDL: `mapdl.aovlap(na1='', na2='', na3='', na4='', na5='', na6='', na7='', na8='', na9='', **kwargs)`

Overlaps areas.

## Parameters

**na1**, **na2**, **na3**, **na4**, **na5**, **na6**, **na7**, **na8**, **na9**: Numbers of areas to be operated on. If `NA1` = ALL, use all selected areas and ignore `NA2` to `NA9`. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1`.

## Notes

Generates new areas which encompass the geometry of all the input areas. The new areas are defined by the regions of intersection of the input areas, and by the complementary (non-intersecting) regions. See [Solid Modeling](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD5_10.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. This operation is only valid when the region of intersection is an area. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AOVLAP.html
