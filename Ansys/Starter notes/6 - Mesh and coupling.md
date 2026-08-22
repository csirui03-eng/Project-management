# Mesh and coupling

Started 2026-08-22. Step 6 of the pipeline, the mesh block of `double_wall.py` and the coupled layer after it.

## Meshing

Meshing is simple. It is literally assign mesh size, then mesh all, and Bob's your uncle. Two settings go before it: `mshape(0, "2D")` for quadrilaterals and `mshkey(0)` for free meshing, which lets the mesher handle the size change at the edge ring instead of forcing a mapped grid. The size loop is the third loop over `DW_DOMAINS`, `AESIZE` per name, and `amesh("ALL")` meshes every area with the attributes stamped on it. Census last time: 708 elements, 94 structure, 84 coupled fluid, 530 uncoupled.

Mesh type (shape and method, a mesher setting) is a different thing from element type (physics and nodes, carried by the areas), and the two have to agree: [[X - Mesh type|Mesh type]].

## Coupled layer

In plain words we are doing the coupling manually. All that means is identifying the edge where the two kinds of element touch and switching the fluid elements there to the coupled variant. The block does exactly those two things: four lines identify (the structure areas, their nodes, every element touching those nodes, the uncoupled air among them), one line switches (`EMODIF` to type 2). They stay FLUID29. Type 2 is the same element with KEYOPT(2)=0, carrying UX and UY as well as PRES, and that is the only place in the air those DOFs exist. The FSI flag is what makes the coupling act: the conversion gives the elements the DOFs, the flag on the wetted faces tells the solver to tie them to the structure. A type 2 element has four faces and only the one on the wall couples, so the flag aims: `SF,ALL,FSI` lands on faces whose nodes are all in the node selection, and the node selection is the wall nodes. The flag line sits right after `emodif`, while that selection is still live (2026-08-23, merged from a second block that rebuilt the same selection).

What we are doing, on the server: selecting every node on the structure areas (`nsla`, boundary nodes included), then highlighting every element owning at least one such node (`esln("S", 0)`, so after it the selected set is those elements, structure and first layer of air alike). `esel("R", "TYPE", "", 3)` keeps only the uncoupled fluid, so we do not convert the structure elements as well. Then `emodif` converts to coupled. It works like selection in the actual software: the Select menu is these commands with buttons, the set persists, and every command after acts on the selected set only. Each entity type keeps its own set, so the node selection from `nsla` is still in force beside the element selection.

The four structure areas are gathered with `cmsel("S", ...)` then `cmsel("A", ...)` three times, select and add, so the conversion runs once over both walls. This is the pattern the element reference asks for (coupled variant at the interface only, pressure only elsewhere). Mechanical does it behind a checkbox. We do it by hand in eight lines. I like our way, it seems more flexible: the layer is defined by adjacency, not by geometry, so moving a wall or changing the gap finds the new layer with the same lines, and the count of 84 converted elements is the proof.

## Table of methods
