---
apdl: "NAXIS"
method: naxis
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.naxis
generated: 2026-08-22
tags: [mapdl-command]
---

# NAXIS

PyMAPDL: `mapdl.naxis(action='', val='', **kwargs)`

Generates nodes for general axisymmetric element sections.

## Parameters

**action**

Specifies one of the following command behaviors:

- `GEN` - Generates nodes around the axis of an axisymmetric section (default).
- `CLEAR` - Clears all nodes around the axis of an axisymmetric section.
- `EFACET` - Specifies the number of facets per edge between nodal planes and integration planes in the circumferential direction to display using PowerGraphics. This option is only valid with [[eshape|/ESHAPE]],1 and [[rsys|RSYS]],SOLU commands.

**val**

Tolerance value or number of facets per edge:

- `TOLER` - When `Action` = GEN, the tolerance to use for merging the generated nodes around the axis.
- `NUM` - When `Action` = EFACET, the number of facets per element edge for element plots:
  - `AUTO` - Use program-chosen facets per edge (default).
  - `1` - Use 1 facet per edge (default for elements with 9, 10, 11, or 12 nodal planes). Shows nodal and integration planes only.
  - `2` - Use 2 facets per edge (default for elements with 5, 6, 7, or 8 nodal planes, and maximum for elements with 9, 10, 11, or 12 nodal planes).
  - `3` - Use 3 facets per edge (default for elements with 3 or 4 nodal planes, and maximum for elements with 6, 7, or 8 nodal planes).
  - `4` - Use 4 facets per edge (maximum for elements with 5 nodal planes).
  - `5` - Use 5 facets per edge (maximum for elements with 4 nodal planes).
  - `6` - Use 6 facets per edge (maximum for elements with 3 nodal planes).

## Notes

The **NAXIS** command generates or clears the nodes for general axisymmetric element sections. The command applies to elements `SURF159`, `SOLID272`, and `SOLID273`.

The generate option ( `Action` = GEN) operates automatically on any current-technology axisymmetric element. Any nodes within the tolerance value ( `TOLER` ) of the axis are merged into a single node. The default tolerance is 1.0e-4.

If you want to change the number of nodes, use the clear option ( `Action` = CLEAR) before regenerating the nodes.

To cause the 3D element plot to appear more like the actual 3D model, use **NAXIS**,EFACET, `NUM`, where `NUM` \> 1. In this case, the coordinate system specified for displaying element and nodal results (RSYS) must be solution ( [[rsys|RSYS]],SOLU); otherwise, Ansys resets `NUM` to 1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NAXIS.html
