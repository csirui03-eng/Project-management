# Mesh type

Started 2026-08-22 from the meshing discussion in [[6 - Mesh and coupling|Mesh and coupling]]. Concept note beside the numbered steps. Reference, written on request.

## Mesh type against element type

Two separate things, set by different commands, and both have to agree.

Element type (`ET`) is what each element is: its physics and its nodes. PLANE183 is a structural element with 8 nodes (corners plus midsides) carrying UX and UY. FLUID29 is an acoustic element with 4 corner nodes carrying PRES, plus UX and UY when coupled. Set in step 5 and stamped on the areas by `AATT`.

Mesh type (`MSHAPE`, `MSHKEY`) is how the mesher cuts an area into cells: the shape of the cells and the method of laying them out. It says nothing about physics. Element type is chosen per domain and carried by the areas. Mesh type is a mesher setting, set once before `AMESH`, applying to everything meshed after it.

The agreement: the element type fixes which shapes are legal. PLANE183 takes quads or triangles (8 or 6 nodes). FLUID29 is a 4 node quad that can degenerate to a triangle. Quads suit both, which is why the script asks for quads everywhere, and free meshing fills in a few triangles where the geometry forces it, as it did at the edge ring in the mesh plots.

## Shape: quadrilateral or triangle

`MSHAPE,0,2D` is quads, `MSHAPE,1,2D` is triangles. The script uses `mapdl.mshape(0, "2D")`.

## Method: mapped or free

Mapped (`MSHKEY,1`) is a regular grid. It needs a four sided area with matching divisions on opposite sides. Free (`MSHKEY,0`) lets the mesher place cells however it can fit them, which is what absorbs the 5 mm to 1.7 mm size change at the edge ring without dividing lines by hand. The script uses `mapdl.mshkey(0)`.
