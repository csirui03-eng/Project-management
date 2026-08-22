---
apdl: "QUAD"
method: quad
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.quad
generated: 2026-08-22
tags: [mapdl-command]
---

# QUAD

PyMAPDL: `mapdl.quad(node1='', nintr='', node2='', nfill='', nstrt='', ninc='', pkfac='', **kwargs)`

Generates a quadratic line of nodes from three nodes.

## Parameters

**node1**: Begin fill-in from this node location. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nintr**: Intermediate or guiding node. Quadratic curve will pass through this location. `NINTR` may have any node number and any location. If the quadratic line also generates a node with number `NINTR`, the generated location overrides the previous `NINTR` location.

**node2**: End quadratic fill-in at this node location.

**nfill**: Fill-in `NFILL` nodes between `NODE1` and `NODE2` (defaults to \| `NODE2` - `NODE1` \|-1). `NFILL` must be positive.

**nstrt**: Node number assigned to first filled-in node (defaults to `NODE1` + `NINC` ).

**ninc**: Add this increment to each of the remaining filled-in node numbers (may be positive or negative). Defaults to ( `NODE2` - `NODE1` )/( `NFILL` + 1), that is, linear interpolation.

**pkfac**: Peak location factor. If `PKFAC` =0.5, the peak of the quadratic shape occurs at the `NINTR` location. If 0.0 \< `PKFAC` \< 0.5, the peak occurs to the `NODE2` side of the `NINTR` location. If 0.5 \< `PKFAC` \< 1.0, the peak occurs to the `NODE1` side of the `NINTR` location. Defaults to 0.5.

## Notes

Generates a quadratic line of nodes (in the active coordinate system) from three nodes. The three nodes determine the plane of the curve and may have been defined in any coordinate system. Any number of nodes may be filled-in and any node number sequence may be assigned.

The quadratic line feature uses three nodes ( `NODE1`, `NINTR`, `NODE2` ) to determine the plane of the curve. The curve passes through the three points, beginning from `NODE1`, through the intermediate (or guiding) point `NINTR`, and toward `NODE2`.

Generated nodes are also quadratically spaced. If the guiding node number is within the set being generated, it will be relocated according to the quadratic spacing.

The peak location factor is used to determine how the quadratic fits through the three points. Various nodal progressions can be obtained by different combinations of `PKFAC` and the guiding node location. If the guiding node is at mid-length between `NODE1` and `NODE2`, 0.293 (equation omitted) `PKFAC` \< 0.707 will ensure that all generated nodes fall within the `NODE1`, `NODE2` bounds. In the limit, as `PKFAC` approaches 0.0, the peak approaches the line through `NODE1` and `NINTR` at an infinite distance from `NODE1`. The **QUAD** command generates quadratic lines of nodes, which in turn may be used as a base line for generating irregular surfaces of nodes (by repeating ( `*REPEAT` ), generating ( [[ngen|NGEN]], [[nscale|NSCALE]] ), etc.). Irregular surfaces may also be generated with the meshing commands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_QUAD.html
