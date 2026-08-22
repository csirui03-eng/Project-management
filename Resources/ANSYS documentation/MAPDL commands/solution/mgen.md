---
apdl: "MGEN"
method: mgen
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.master_dof.MasterDof.mgen
generated: 2026-08-22
tags: [mapdl-command]
---

# MGEN

PyMAPDL: `mapdl.mgen(itime='', inc='', node1='', node2='', ninc='', **kwargs)`

Generates additional MDOF from a previously defined set.

## Parameters

**itime**, **inc**: Do this generation operation a total of `ITIME` s, incrementing all nodes in the set by `INC` each time after the first. `ITIME` must be \> 1 for generation to occur. All previously defined master degree of freedom directions are included in the set. A component name may also be substituted for `ITIME`.

**node1**, **node2**, **ninc**: Generate master degrees of freedom from set beginning with `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and set is all selected nodes ( [[nsel|NSEL]] ). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Generates additional master degrees of freedom from a previously defined set. If used in SOLUTION, this command is valid only within the first load step.

For the free-interface ( [[cmsopt|CMSOPT]], FREE) and residual-flexible free-interface ( [[cmsopt|CMSOPT]], RFFB) CMS method analyses, pseudo-constraints could have been applied on some master degrees of freedom of the previously defined set (SUPPORT = ON in the [[m|M]] command). The master degrees of freedom generated from these with the **MGEN** command are also defined with pseudo-constraints.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MGEN.html
