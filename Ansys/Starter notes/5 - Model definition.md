# Model definition

Started 2026-08-22. Step 5 of the pipeline. Bookkeeping heavy, conceptually simple.

Usually it is preferable to contain everything model set up related in its own script. Here that is `double_wall.py`, and it runs from the parameters, through geometry creation, naming, attributes, meshing and the flags, up to the boundary conditions. Everything that is the model lives there. 
## Set up

It is straightforward. We have geometry parameters, element type assignment to numbers, and material assignment to numbers. That is our set up.

The material numbers take their values from a parameter dict too (`DW_MAT`), the same way the geometry does from `DW_GEOM`: values in one place, assignments in another. The element type assignment carries the KEYOPTs: axisymmetric on all three types, and the one switch that separates type 2 from type 3, coupled (UX, UY, PRES) or pressure only.

## Geometry

We start by setting up the parametric values, as we would in a normal solver creating a normal model. We then move to geometry creation. Geometry creation is usually the iterative step: `double_wall.py` is a live document, the notebook is started and running, the server is started and the client is attached to it.

The area numbers in the domain viewer are natural numbering that does not mean much. They only serve to indicate that one particular section is in fact a distinct domain from another. They also change under you: gluing retired areas 2 to 8 and issued 9 to 15 for the glued versions, which is why naming happens only after `aglue`.

![[domain viewer 2026-08-22.png]]
The domain viewer, cell 7: `aplot` with areas coloured and numbered after the rebuild.

## Naming by component

This section is important because we want names assigned to the key domains, as a way for us to assign key information to those domains: material and element type, mesh size, the coupling layer and the flags, and the counts in the audit cells. Coordinates appear here for the last time. Downstream stages speak names. Names survive renumbering, which area numbers do not, and they read as the model (`W1_EDGE_A`) rather than as a coordinate band.

![[component check 2026-08-22.png]]
The component check, cell 8: every component with its entity numbers, read against the numbered plot. `SOURCE_L` holds line 3, `AIR_UP_A` holds the two areas either side of the source line.

## Table of methods

Methods used in the script, in call order. Each PyMAPDL method is the APDL command in lower case, which is the key into the MAPDL command reference.

| Method | APDL | Does |
|---|---|---|
| `mapdl.clear()` | `/CLEAR` | wipe the database, keep the jobname and working directory |
| `mapdl.prep7()` | `/PREP7` | enter the preprocessor, where model building commands are accepted |
| `mapdl.et(n, name)` | `ET` | define element type number n |
| `mapdl.keyopt(n, k, v)` | `KEYOPT` | set option k of element type n (axisymmetric, coupled or not) |
| `mapdl.mp(label, n, value)` | `MP` | set material property label on material number n |
| `mapdl.rectng(x1, x2, y1, y2)` | `RECTNG` | create a rectangular area by its corner coordinates |
| `mapdl.aglue("ALL")` | `AGLUE` | glue coincident area boundaries so neighbours share lines, renumbers areas |

For naming, coming next: `asel` (`ASEL`, select areas by location), `lsel` (`LSEL`, select lines), `cm` (`CM`, name the current selection as a component), `allsel` (`ALLSEL`, select everything again).
