---
apdl: "TIMP"
method: timp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.timp
generated: 2026-08-22
tags: [mapdl-command]
---

# TIMP

PyMAPDL: `mapdl.timp(elem='', chgbnd='', implevel='', **kwargs)`

Improves the quality of tetrahedral elements that are not associated with a volume.

## Parameters

**elem**: Identifies the tetrahedral elements to be improved. Valid values are ALL and P. If `ELEM` = ALL (default), improve all selected tetrahedral elements. If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**chgbnd**

Specifies whether to allow boundary modification. Boundary modification includes such things as changes in the connectivity of the element faces on the boundary and the addition of boundary nodes. (Also see the Notes section below for important usage information for `CHGBND`.)

- `0` - Do not allow boundary modification.
- `1` - Allow boundary modification (default).

**implevel**

Identifies the level of improvement to be performed on the elements. (Improvement occurs primarily through the use of face swapping and node smoothing techniques.)

- `0` - Perform the least amount of swapping/smoothing.
- `1` - Perform an intermediate amount of swapping/smoothing.
- `2` - Perform the greatest amount of swapping/smoothing.
- `3` - Perform the greatest amount of swapping/smoothing, plus additional improvement techniques (default).

## Notes

The **TIMP** command enables you to improve a given tetrahedral mesh by reducing the number of poorly-shaped tetrahedral elements (in particular, the number of sliver tetrahedral elements)-as well as the overall number of elements-in the mesh. It also improves the overall quality of the mesh.

**TIMP** is particularly useful for an imported tetrahedral mesh for which no geometry information is attached.

Regardless of the value of the `CHGBND` argument, boundary mid-nodes can be moved.

When loads or constraints have been placed on boundary nodes or mid-nodes, and boundary mid-nodes are later moved, the program issues a warning message to let you know that it will not update the loads or constraints.

No boundary modification is performed if shell or beam elements are present in the mesh, even when `CHGBND` = 1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TIMP.html
