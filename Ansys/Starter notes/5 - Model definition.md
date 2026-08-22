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

## Attributes

The basic version: with a name assigned to the critical domains and edges, we now start assigning properties to them. There are many ways to do this, but the best way is three execution loops (naming, attributes, mesh sizes) that carry out an assignment already written down, in rather plain words, in the parameter set up section as a simple dictionary, `DW_DOMAINS`. This section is the second of the three loops: select the name, stamp its material and element type on the areas with `AATT`, select everything again. The mesher reads the stamps when it gets there.

For people who know coding this is the usual rule: the last line in a loop resets the state to the default state. Here the loop shape is narrow the selection with `S` (a new set, so the state before does not matter), do the work, then go back to `allsel()`. The trailing `allsel()` is the one that counts: the next cell, the next loop, and the other client on the same server all inherit whatever selection is current. `ALLSEL` restores entities, not components, so a loop that went in through `CMSEL,S` is restored with `CMSEL,ALL`.

## Table of methods

Methods used in the script, in call order. Each PyMAPDL method is the APDL command in lower case, which is the key into the MAPDL command reference.

| Method | APDL | Does |
|---|---|---|
| `mapdl.clear()` | [[clear\|/CLEAR]] | wipe the database, keep the jobname and working directory |
| `mapdl.prep7()` | [[prep7\|/PREP7]] | enter the preprocessor, where model building commands are accepted |
| `mapdl.et(n, name)` | [[et\|ET]] | define element type number n |
| `mapdl.keyopt(n, k, v)` | [[keyopt\|KEYOPT]] | set option k of element type n (axisymmetric, coupled or not) |
| `mapdl.mp(label, n, value)` | [[mp\|MP]] | set material property label on material number n |
| `mapdl.rectng(x1, x2, y1, y2)` | [[rectng\|RECTNG]] | create a rectangular area by its corner coordinates |
| `mapdl.aglue("ALL")` | [[aglue\|AGLUE]] | glue coincident area boundaries so neighbours share lines, renumbers areas |
| `mapdl.asel("S", "LOC", "Y", a, b)` | [[asel\|ASEL]] | select areas by location, S new set, R narrow the current set |
| `mapdl.lsel("S", "LOC", "Y", y)` | [[lsel\|LSEL]] | select lines by location, same modes |
| `mapdl.cm(name, "AREA")` | [[cm\|CM]] | name the current selection as a component of that entity type |
| `mapdl.allsel()` | [[allsel\|ALLSEL]] | select every entity again (components themselves need `CMSEL,ALL`) |
| `mapdl.cmsel("S", name)` | [[cmsel\|CMSEL]] | select a component by name, same modes as ASEL |
| `mapdl.aatt(mat, "", type)` | [[aatt\|AATT]] | stamp material and element type on the selected areas, read by the mesher |
