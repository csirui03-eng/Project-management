# Model definition

Started 2026-08-22. Step 5 of the pipeline, `double_wall.py` up to the geometry. Bookkeeping heavy, conceptually simple.

## Set up

It is straightforward. We have geometry parameters, element type assignment to numbers, and material assignment to numbers. That is our set up.

The material numbers take their values from a parameter dict too (`DW_MAT`), the same way the geometry does from `DW_GEOM`: values in one place, assignments in another. The element type assignment carries the KEYOPTs: axisymmetric on all three types, and the one switch that separates type 2 from type 3, coupled (UX, UY, PRES) or pressure only.

## Geometry

## Naming by component
