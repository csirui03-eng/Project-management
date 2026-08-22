---
apdl: "NORA"
method: nora
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nora
generated: 2026-08-22
tags: [mapdl-command]
---

# NORA

PyMAPDL: `mapdl.nora(area='', ndir='', **kwargs)`

Rotates nodal coordinate systems to surface normal

## Parameters

**area**: The area number containing the nodes to be rotated to their normals. If ALL, applies to all selected areas (see the [[asel|ASEL]] command). If AREA = P, graphical picking is enabled.

**ndir**: Direction of the normal. If NDIR = -1, the nodal coordinate system is rotated in the opposite direction of the surface normal. The default is the same direction as the surface normal.

## Notes

The NORA command rotates the X-axis of the nodal coordinate system to the surface normal. The rotated nodal coordinate systems may be displayed through the [[psymb|/PSYMB]] command. In case multiple areas are selected, there could be conflicts at the boundaries. If a node belongs to two areas that have a different normal, its nodal coordinate system will be rotated to the area normal with the lowest number. You can use the [[areverse|AREVERSE]] and [[anorm|ANORM]] commands to rotate the surface normals in the appropriate direction. Keep the following in mind when using the NORA command:

- If the nodal coordinate system is parallel to the global Cartesian system, it is not displayed through the [[psymb|/PSYMB]] command.
- Previously specified rotation on the selected nodes are overridden.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NORA.html
