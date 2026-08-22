---
apdl: "NORL"
method: norl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.norl
generated: 2026-08-22
tags: [mapdl-command]
---

# NORL

PyMAPDL: `mapdl.norl(line='', area='', ndir='', **kwargs)`

Rotates nodal coordinate systems perpendicular to line normal

## Parameters

**line**: Line number containing the nodes to be rotated. If ALL, applies to all selected lines (see the [[lsel|LSEL]] command). If `LINE` = P, graphical picking is enabled.

**area**: The area number containing the selected lines. The normal of the line(s) selected is supposed to lie on this area. Defaults to the lowest numbered selected area containing the line number.

**ndir**: Direction of the normal. If `NDIR` = -1, the nodal coordinate system is rotated in the opposite direction of the line normal. The default is the same direction as the surface normal.

## Notes

The NORL command rotates the X-axis of the nodal coordinate perpendicular to the line normal. The rotated nodal coordinate systems may be displayed through the [[psymb|/PSYMB]] command. In case multiple lines are selected, there could be conflicts at the boundaries. If a node belongs to two lines that have a different normal, its nodal coordinate system will be rotated to the line normal with the lowest number. Keep the following in mind when using the NORL command:

- If the nodal coordinate system is parallel to the global Cartesian system, it is not displayed through the [[psymb|/PSYMB]] command.
- Previously specified rotation on the selected nodes are overridden.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NORL.html
