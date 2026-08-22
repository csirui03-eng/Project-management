---
apdl: "NGEN"
method: ngen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.ngen
generated: 2026-08-22
tags: [mapdl-command]
---

# NGEN

PyMAPDL: `mapdl.ngen(itime='', inc='', node1='', node2='', ninc='', dx='', dy='', dz='', space='', **kwargs)`

Generates additional nodes from a pattern of nodes.

## Parameters

**itime**, **inc**: Do this generation operation a total of `ITIME` times, incrementing all nodes in the given pattern by `INC` each time after the first. `ITIME` must be \> 1 for generation to occur.

**node1**, **node2**, **ninc**: Generate nodes from the pattern of nodes beginning with `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and the pattern is all selected nodes ( [[nsel|NSEL]] ). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

**dx**, **dy**, **dz**: Node location increments in the active coordinate system (DR, Dθ, DZ for cylindrical, DR, Dθ, DΦ for spherical or toroidal).

**space**

Spacing ratio. Ratio of last division size to first division size. If \> 1.0, divisions increase. If \< 1.0, divisions decrease. Ratio defaults to 1.0 (uniform spacing).

The average spacing ratio remains 1.0, such that the location of the last generated set will be the same regardless of `SPACE`. `SPACE` only serves to skew the position of the nodes between the pattern set and the last set.

## Notes

Generates additional nodes from a given node pattern. Generation is done in the active coordinate system. Nodes in the pattern may have been generated in any coordinate system.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NGEN.html
