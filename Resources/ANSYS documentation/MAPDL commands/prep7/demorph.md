---
apdl: "DEMORPH"
method: demorph
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.morphing.Morphing.demorph
generated: 2026-08-22
tags: [mapdl-command]
---

# DEMORPH

PyMAPDL: `mapdl.demorph(elem='', dimn='', rmshky='', **kwargs)`

Move nodes in selected elements to conform to structural displacements.

## Parameters

**elem**: Non-structural elements to which mesh movement (morph) applies. If ALL, apply morphing to all selected elements ( [[esel|ESEL]] ). If ELEM = P, graphical picking is enabled. A component may be substituted for ELEM.

**dimn**: Problem dimensionality. Use "2" for a 2D problem and "3" for a 3D problem (no default).

**rmshky**

Remesh flag option:

- `0` - Remesh the selected non-structural regions only if mesh morphing fails.
- `1` - Remesh the selected non-structural regions and bypass mesh morphing.
- `2` - Perform mesh morphing only and do not remesh.

## Notes

The selected elements should include only non-structural regions adjacent to structural regions. The exterior nodes of the selected elements will usually be on the boundary of the region which will have node positions displaced. For `DIMN` = 2, elements must lie on a flat plane. The **DEMORPH** command requires a single domain grouping of elements be provided (multiple domains of elements are not permitted). Exterior nodes will be assumed fixed (no nodes will be morphed) unless they coincide with structural nodes having nonzero displacements.

Nodes in the structural regions move in accordance with computed displacements. Displacements from a structural analysis must be in the database prior to issuing **DEMORPH**.

By default ( `RMSHKY` = 0), **DEMORPH** will remesh the selected non-structural regions entirely if a satisfactory morphed mesh cannot be provided.

If boundary conditions and loads are applied directly to nodes and elements, the **DEMORPH** command requires that these be removed before remeshing can take place.

Exercise care with initial conditions defined by the [[ic|IC]] command. Before a structural analysis is performed for a sequentially coupled analysis, the **DEMORPH** command requires that initial conditions be removed from all null element type nodes in the non-structural regions. Use [[icdele|ICDELE]] to delete the initial conditions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DEMORPH.html
