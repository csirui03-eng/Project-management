---
apdl: "ENORM"
method: enorm
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.enorm
generated: 2026-08-22
tags: [mapdl-command]
---

# ENORM

PyMAPDL: `mapdl.enorm(enum='', **kwargs)`

Reorients shell element normals or line element node connectivity.

## Parameters

**enum**: Element number having the normal direction that the reoriented elements are to match. If `ENUM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Reorients shell elements so that their outward normals are consistent with that of a specified element. **ENORM** can also be used to reorder nodal connectivity of line elements so that their nodal ordering is consistent with that of a specified element.

For shell elements, the operation reorients the element by reversing and shifting the node connectivity pattern. For example, for a 4-node shell element, the nodes in positions I, J, K and L of the original element are placed in positions J, I, L and K of the reoriented element. All 3D shell elements in the selected set are considered for reorientation, and no element is reoriented more than once during the operation. Only shell elements adjacent to the lateral (side) faces are considered.

The command reorients the shell element normals on the same panel as the specified shell element. A panel is the geometry defined by a subset of shell elements bounded by free edges or T-junctions (anywhere three or more shell edges share common nodes).

Reorientation progresses within the selected set until either of the following conditions is true:

- The edge of the model is reached.
- More than two elements (whether selected or unselected) are adjacent to a lateral face.

In situations where unselected elements might undesirably cause case b to control, consider using  
[[ensym|ENSYM]],0,,0,ALL instead of **ENORM**. It is recommended that reoriented elements be displayed and graphically reviewed.

You cannot use the **ENORM** command to change the normal direction of any element that has a body or surface load. We recommend that you apply all of your loads only after ensuring that the element normal directions are acceptable.

Real constant values are not reoriented and may be invalidated by an element reversal.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ENORM.html
