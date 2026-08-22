---
apdl: "FILL"
method: fill
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.fill
generated: 2026-08-22
tags: [mapdl-command]
---

# FILL

PyMAPDL: `mapdl.fill(node1='', node2='', nfill='', nstrt='', ninc='', itime='', inc='', space='', **kwargs)`

Generates a line of nodes between two existing nodes.

## Parameters

**node1**, **node2**: Beginning and ending nodes for fill-in. `NODE1` defaults to next to last node specified, `NODE2` defaults to last node specified. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nfill**: Fill `NFILL` nodes between `NODE1` and `NODE2` (defaults to \| `NODE2` - `NODE1` \|-1). `NFILL` must be positive.

**nstrt**: Node number assigned to first filled-in node (defaults to `NODE1` + `NINC` ).

**ninc**: Add this increment to each of the remaining filled-in node numbers (may be positive or negative). Defaults to the integer result of ( `NODE2` - `NODE1` )/( `NFILL` + 1), that is, linear interpolation. If the default evaluates to zero, or if zero is input, `NINC` is set to 1.

**itime**, **inc**: Do fill-in operation a total of `ITIMEs`, incrementing `NODE1`, `NODE2` and `NSTRT` by `INC` each time after the first. `ITIME` and `INC` both default to 1.

**space**: Spacing ratio. Ratio of last division size to first division size. If \> 1.0, divisions increase. If \< 1.0, divisions decrease. Ratio defaults to 1.0 (uniform spacing).

## Notes

Generates a line of nodes (in the active coordinate system) between two existing nodes. The two nodes may have been defined in any coordinate system. Nodal locations and rotation angles are determined by interpolation. Any number of nodes may be filled-in and any node number sequence may be assigned. See the [[cscir|CSCIR]] command when filling across the 180° singularity line in a non- Cartesian system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILL.html
