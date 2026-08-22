---
apdl: "VIMP"
method: vimp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.vimp
generated: 2026-08-22
tags: [mapdl-command]
---

# VIMP

PyMAPDL: `mapdl.vimp(vol='', chgbnd='', implevel='', **kwargs)`

Improves the quality of the tetrahedral elements in the selected volume(s).

## Parameters

**vol**: Number of the volume containing the tetrahedral elements to be improved. If `VOL` = ALL (default), improve the tetrahedral elements in all selected volumes. If `VOL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `VOL`.

**chgbnd**

Specifies whether to allow boundary modification. Boundary modification includes such things as changes in the connectivity of the element faces on the boundary and the addition of boundary nodes. (Also see [[vimp#Notes|VIMP]] below for important usage information for `CHGBND`.)

- `0` - Do not allow boundary modification.
- `1` - Allow boundary modification (default).

**implevel**

Identifies the level of improvement to be performed on the elements. (Improvement occurs primarily through the use of face swapping and node smoothing techniques.)

- `0` - Perform the least amount of swapping/smoothing.
- `1` - Perform an intermediate amount of swapping/smoothing.
- `2` - Perform the greatest amount of swapping/smoothing.
- `3` - Perform the greatest amount of swapping/smoothing, plus additional improvement techniques (default).

## Notes

**VIMP** is useful for further improving a volume mesh created in Mechanical APDL ( [[vmesh|VMESH]] ), especially quadratic tetrahedral element meshes.

The command enables you to improve a given tetrahedral mesh by reducing the number of poorly-shaped tetrahedral elements (in particular, the number of sliver tetrahedral elements)-as well as the overall number of elements-in the mesh. It also improves the overall quality of the mesh.

Regardless of the value of the `CHGBND` argument, boundary mid-nodes can be moved.

When loads or constraints have been placed on boundary nodes or mid-nodes, and boundary mid-nodes are later moved, the program issues a warning message indicating that it will not update the loads or constraints.

Even when `CHGBND` = 1, no boundary modification is performed on areas and lines that are not modifiable. For example, areas that are adjacent to other volumes or that contain shell elements, or lines that are not incident on modifiable areas, contain beam elements, or have line divisions specified for them ( [[lesize|LESIZE]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VIMP.html
