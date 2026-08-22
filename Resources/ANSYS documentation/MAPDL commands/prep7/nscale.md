---
apdl: "NSCALE"
method: nscale
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nscale
generated: 2026-08-22
tags: [mapdl-command]
---

# NSCALE

PyMAPDL: `mapdl.nscale(inc='', node1='', node2='', ninc='', rx='', ry='', rz='', **kwargs)`

Generates a scaled set of nodes from a pattern of nodes.

## Parameters

**inc**: Do this scaling operation one time, incrementing all nodes in the given pattern by `INC`. If `INC` = 0, nodes will be redefined at the scaled locations.

**node1**, **node2**, **ninc**: Scale nodes from pattern of nodes beginning with `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and pattern is all selected nodes ( [[nsel|NSEL]] ). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

**rx**, **ry**, **rz**: Scale factor ratios. Scaling is relative to the origin of the active coordinate system (RR, Rθ, RZ for cylindrical, RR, Rθ, RΦ for spherical or toroidal). If absolute value of ratio \> 1.0, pattern is enlarged. If \< 1.0, pattern is reduced. Ratios default to 1.0 (each).

## Notes

Generates a scaled pattern of nodes from a given node pattern. Scaling is done in the active coordinate system. Nodes in the pattern may have been generated in any coordinate system.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSCALE.html
