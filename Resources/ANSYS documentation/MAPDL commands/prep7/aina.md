---
apdl: "AINA"
method: aina
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.aina
generated: 2026-08-22
tags: [mapdl-command]
---

# AINA

PyMAPDL: `mapdl.aina(na1='', na2='', na3='', na4='', na5='', na6='', na7='', na8='', na9='', **kwargs)`

Finds the intersection of areas.

## Parameters

**na1**, **na2**, **na3**, **na4**, **na5**, **na6**, **na7**, **na8**, **na9**: Numbers of areas to be intersected. If `NA1` = ALL, `NA2` to `NA9` are ignored and the intersection of all selected areas is found. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1`.

## Notes

Finds the common (not pairwise) intersection of areas. The common intersection is defined as the regions shared (in common) by **all** areas listed on this command. New areas will be generated where the original areas intersect. If the regions of intersection are only lines, new lines will be generated instead. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AINA.html
