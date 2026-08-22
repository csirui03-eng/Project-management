---
apdl: "DAMORPH"
method: damorph
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.morphing.Morphing.damorph
generated: 2026-08-22
tags: [mapdl-command]
---

# DAMORPH

PyMAPDL: `mapdl.damorph(area='', xline='', rmshky='', **kwargs)`

Move nodes in selected areas to conform to structural displacements.

## Parameters

**area**: Non-structural area to which mesh movement (morph) applies. If ALL, apply morphing to all selected areas \[ASEL\]. If `AREA` = P, graphical picking is enabled. A component may be substituted for `AREA`.

**xline**: Lines to be excluded from morphing. If ALL, exclude all selected lines \[LSEL\] from morphing. If `XLINE` = P, graphical picking is enabled. A component may be substituted for `XLINE`. If `XLINE` is blank (default), allow morphing of nodes attached to lines of the selected areas ( `AREA` ) which are not shared by unselected areas. See Notes for clarification.

**rmshky**

Remesh flag option:

- `0` - Remesh the selected non-structural areas only if mesh morphing fails.
- `1` - Remesh the selected non-structural areas and bypass mesh morphing.
- `2` - Perform mesh morphing only and do not remesh.

## Notes

The selected areas should include only non-structural regions adjacent to structural regions. **DAMORPH** will morph the non-structural areas to coincide with the deflections of the structural regions.

Nodes in the structural regions move in accordance with computed displacements. Displacements from a structural analysis must be in the database prior to issuing **DAMORPH**.

By default, nodes attached to lines can move along the lines, or off the lines (if a line is interior to the selected areas). You can use `XLINE` to restrain nodes on certain lines.

By default ( `RMSHKEY` = 0), **DAMORPH** will remesh the selected non-structural areas entirely if a satisfactory morphed mesh cannot be provided.

If boundary conditions and loads are applied directly to nodes and elements, the **DAMORPH** command requires that these be removed before remeshing can take place.

Exercise care with initial conditions defined by the [[ic|IC]] command. Before a structural analysis is performed for a sequentially coupled analysis, the **DAMORPH** command requires that initial conditions be removed from all null element type nodes in the non-structural regions. Use [[icdele|ICDELE]] to delete the initial conditions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DAMORPH.html
