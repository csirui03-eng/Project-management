# Mesh and coupling

Started 2026-08-22. Step 6 of the pipeline, the mesh block of `double_wall.py` and the coupled layer after it.

## Meshing

Meshing is simple. It is literally assign mesh size, then mesh all, and Bob's your uncle. Two settings go before it: `mshape(0, "2D")` for quadrilaterals and `mshkey(0)` for free meshing, which lets the mesher handle the size change at the edge ring instead of forcing a mapped grid. The size loop is the third loop over `DW_DOMAINS`, `AESIZE` per name, and `amesh("ALL")` meshes every area with the attributes stamped on it. Census last time: 708 elements, 94 structure, 84 coupled fluid, 530 uncoupled.

Mesh type (shape and method, a mesher setting) is a different thing from element type (physics and nodes, carried by the areas), and the two have to agree: [[X - Mesh type|Mesh type]].

## Coupled layer

In plain words we are doing the coupling manually. All that means is identifying the edge where the two kinds of element touch and switching the fluid elements there to the coupled variant. The block does exactly those two things: four lines identify (the structure areas, their nodes, every element touching those nodes, the uncoupled air among them), one line switches (`EMODIF` to type 2). They stay FLUID29. Type 2 is the same element with KEYOPT(2)=0, carrying UX and UY as well as PRES, and that is the only place in the air those DOFs exist. The FSI flag block that follows is what makes the coupling act: the conversion gives the elements the DOFs, the flag on the wetted faces tells the solver to tie them to the structure.

## Table of methods
