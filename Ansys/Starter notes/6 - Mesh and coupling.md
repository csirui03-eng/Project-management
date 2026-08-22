# Mesh and coupling

Started 2026-08-22. Step 6 of the pipeline, the mesh block of `double_wall.py` and the coupled layer after it.

## Meshing

Meshing is simple. It is literally assign mesh size, then mesh all, and Bob's your uncle. Two settings go before it: `mshape(0, "2D")` for quadrilaterals and `mshkey(0)` for free meshing, which lets the mesher handle the size change at the edge ring instead of forcing a mapped grid. The size loop is the third loop over `DW_DOMAINS`, `AESIZE` per name, and `amesh("ALL")` meshes every area with the attributes stamped on it. Census at the first mesh: 708 elements, 94 structure, 84 coupled fluid, 530 uncoupled. At the converged mesh: 1858, 868 structure, 248 coupled, 742 uncoupled.

Mesh type (shape and method, a mesher setting) is a different thing from element type (physics and nodes, carried by the areas), and the two have to agree: [[X - Mesh type|Mesh type]].

Langfeldt's thesis states the element size rule as min(λ_min, L_x, L_y)/6: six per shortest wavelength and six across the thinnest dimension of every region. The air at 5 mm passes both (34 per wavelength at 2 kHz, 8 across the gap). The first mesh did not on the structure: 2 through the wall, 3 across the edge ring. The convergence study (`LLM\mesh_convergence.py`, 2026-08-23, four levels in under three minutes) moved the lower dip 10 Hz and the 1600 Hz feature 25 Hz between that mesh and 6 across, then nothing further when the air was halved too. Wall and edge at 0.83 mm is the converged default, 1858 elements, 47 s per sweep.

![[mesh convergence 2026-08-23.png]]

## Coupled layer

In plain words we are doing the coupling manually. All that means is identifying the edge where the two kinds of element touch and switching the fluid elements there to the coupled variant. The block does exactly those two things: four lines identify (the structure areas, their nodes, every element touching those nodes, the uncoupled air among them), one line switches (`EMODIF` to type 2). They stay FLUID29. Type 2 is the same element with KEYOPT(2)=0, carrying UX and UY as well as PRES, and that is the only place in the air those DOFs exist. The FSI flag is what makes the coupling act: the conversion gives the elements the DOFs, the flag on the wetted faces tells the solver to tie them to the structure. A type 2 element has four faces and only the one on the wall couples, so the flag aims: `SF,ALL,FSI` lands on faces whose nodes are all in the node selection, and the node selection is the wall nodes. The flag line sits right after `emodif`, while that selection is still live (2026-08-23, merged from a second block that rebuilt the same selection).

What we are doing, on the server: selecting every node on the structure areas (`nsla`, boundary nodes included), then highlighting every element owning at least one such node (`esln("S", 0)`, so after it the selected set is those elements, structure and first layer of air alike). `esel("R", "TYPE", "", 3)` keeps only the uncoupled fluid, so we do not convert the structure elements as well. Then `emodif` converts to coupled. It works like selection in the actual software: the Select menu is these commands with buttons, the set persists, and every command after acts on the selected set only. Each entity type keeps its own set, so the node selection from `nsla` is still in force beside the element selection.

The four structure areas are gathered with `cmsel("S", ...)` then `cmsel("A", ...)` three times, select and add, so the conversion runs once over both walls. This is the pattern the element reference asks for (coupled variant at the interface only, pressure only elsewhere). Mechanical does it behind a checkbox. We do it by hand in eight lines. I like our way, it seems more flexible: the layer is defined by adjacency, not by geometry, so moving a wall or changing the gap finds the new layer with the same lines, and the count of 84 converted elements is the proof.

## Table of methods

Methods used in the mesh and coupling blocks, in call order. The APDL column links to the converted command page in `Resources\ANSYS documentation`.

| Method | APDL | Does |
|---|---|---|
| `mapdl.mshape(0, "2D")` | [[mshape\|MSHAPE]] | cell shape for area meshing, 0 quadrilateral, 1 triangle |
| `mapdl.mshkey(0)` | [[mshkey\|MSHKEY]] | meshing method, 0 free, 1 mapped |
| `mapdl.aesize("ALL", size)` | [[aesize\|AESIZE]] | element edge size on the selected areas |
| `mapdl.amesh("ALL")` | [[amesh\|AMESH]] | mesh the selected areas with their stamped attributes |
| `mapdl.nsla("S", 1)` | [[nsla\|NSLA]] | select nodes belonging to the selected areas, 1 includes boundary nodes |
| `mapdl.esln("S", 0)` | [[esln\|ESLN]] | select elements attached to the selected nodes, 0 any node, 1 all nodes |
| `mapdl.esel("R", "TYPE", "", n)` | [[esel\|ESEL]] | select elements by attribute, here element type, R narrows |
| `mapdl.emodif("ALL", "TYPE", n)` | [[emodif\|EMODIF]] | change an attribute of the selected elements in place |
| `mapdl.sf("ALL", "FSI")` | [[sf\|SF]] | surface flag or load on faces of the selected elements whose nodes are all selected |
