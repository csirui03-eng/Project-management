---
apdl: "AREFINE"
method: arefine
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.arefine
generated: 2026-08-22
tags: [mapdl-command]
---

# AREFINE

PyMAPDL: `mapdl.arefine(na1='', na2='', ninc='', level='', depth='', post='', retain='', **kwargs)`

Refines the mesh around specified areas.

## Parameters

**na1**, **na2**, **ninc**: Areas ( `NA1` to `NA2` in increments of `NINC` ) around which the mesh is to be refined. `NA2` defaults to `NA1`, and `NINC` defaults to 1. If `NA1` = ALL, `NA2` and `NINC` are ignored and all selected areas are used for refinement. If `NA1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

**level**: Amount of refinement to be done. Specify the value of `LEVEL` as an integer from 1 to 5, where a value of 1 provides minimal refinement, and a value of 5 provides maximum refinement (defaults to 1).

**depth**: Depth of mesh refinement in terms of the number of elements outward from the indicated areas (defaults to 1).

**post**

Type of postprocessing to be done after element splitting, in order to improve element quality:

- `OFF` - No postprocessing will be done.
- `SMOOTH` - Smoothing will be done. Node locations may change.
- `CLEAN` - Smoothing and cleanup will be done. Existing elements may be deleted, and node locations may change (default).

**retain**

Flag indicating whether quadrilateral elements must be retained in the refinement of an all- quadrilateral mesh. (The Mechanical APDL program ignores the `RETAIN` argument when you are refining anything other than a quadrilateral mesh.)

- `ON` - The final mesh will be composed entirely of quadrilateral elements, regardless of the element quality (default).
- `OFF` - The final mesh may include some triangular elements in order to maintain element quality and provide transitioning.

## Notes

**AREFINE** performs local mesh refinement around the specified areas. By default, the indi cated elements are split to create new elements with 1/2 the edge length of the original elements ( `LEVEL` = 1).

**AREFINE** refines all area elements and tetrahedral volume elements that are adjacent to the specified areas. Any volume elements that are adjacent to the specified areas, but are not tetrahedra (for example, hexahedra, wedges, and pyramids), are not refined.

You cannot use mesh refinement on a solid model that contains initial conditions at nodes ( [[ic|IC]] ), coupled nodes ( [[cp|CP]] family of commands), constraint equations ( [[ce|CE]] family of commands), or boundary conditions or loads applied directly to any of its nodes or elements. This applies to nodes and elements anywhere in the model, not just in the region where you want to request mesh refinement. See [Revising Your Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD8_6.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for additional restrictions on mesh refinement.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AREFINE.html
