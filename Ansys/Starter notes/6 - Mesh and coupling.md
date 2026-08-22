# Mesh and coupling

Started 2026-08-22. Step 6 of the pipeline, the mesh block of `double_wall.py` and the coupled layer after it.

## Meshing

Meshing is simple. It is literally assign mesh size, then mesh all, and Bob's your uncle. Two settings go before it: `mshape(0, "2D")` for quadrilaterals and `mshkey(0)` for free meshing, which lets the mesher handle the size change at the edge ring instead of forcing a mapped grid. The size loop is the third loop over `DW_DOMAINS`, `AESIZE` per name, and `amesh("ALL")` meshes every area with the attributes stamped on it. Census last time: 708 elements, 94 structure, 84 coupled fluid, 530 uncoupled.

## Coupled layer

## Table of methods
