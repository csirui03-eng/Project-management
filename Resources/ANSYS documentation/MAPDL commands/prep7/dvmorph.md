---
apdl: "DVMORPH"
method: dvmorph
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.morphing.Morphing.dvmorph
generated: 2026-08-22
tags: [mapdl-command]
---

# DVMORPH

PyMAPDL: `mapdl.dvmorph(volu='', xarea='', rmshky='', **kwargs)`

Move nodes in selected volumes to conform to structural displacements.

## Parameters

**volu**: Non-structural volume to which mesh movement (morph) applies. If ALL, apply morphing to all selected volumes ( [[vsel|VSEL]] ). If `VOLU` = P, graphical picking is enabled. A component may be substituted for `VOLU`.

**xarea**: Areas to be excluded from morphing. If ALL, exclude all selected areas ( [[asel|ASEL]] ). If `XAREA` = P, graphical picking is enabled. A component may be substituted for `XAREA`. If `XAREA` is blank (default), allow morphing of nodes attached to areas of the selected volumes ( `VOLU` ) which are not shared by unselected volumes. (See Notes for clarification).

**rmshky**

Remesh flag option:

- `0` - Remesh the selected non-structural volumes only if mesh morphing fails.
- `1` - Remesh the selected non-structural volumes and bypass mesh morphing.
- `2` - Perform mesh morphing only and do not remesh.

## Notes

The selected volumes should include only non-structural regions adjacent to structural regions. DVMORPH will morph the non-structural volumes to coincide with the deflections of the structural regions.

Nodes in the structural regions move in accordance with computed displacements. Displacements from a structural analysis must be in the database prior to issuing DVMORPH.

By default, nodes attached to areas can move along the areas. You can use `XAREA` to restrain nodes on certain areas.

By default ( `RMSHKY` = 0), DVMORPH will remesh the selected non-structural volumes entirely if a satisfactory morphed mesh cannot be provided.

If boundary conditions and loads are applied directly to nodes and elements, the DVMORPH command requires that these be removed before remeshing can take place.

Exercise care with initial conditions defined by the [[ic|IC]] command. Before a structural analysis is performed for a sequentially coupled analysis, the DVMORPH command requires that initial conditions be removed from all null element type nodes in the non-structural regions. Use [[icdele|ICDELE]] to delete the initial conditions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DVMORPH.html
