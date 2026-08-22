---
apdl: "PLVECT"
method: plvect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.plvect
generated: 2026-08-22
tags: [mapdl-command]
---

# PLVECT

PyMAPDL: `mapdl.plvect(item='', lab2='', lab3='', labp='', mode='', loc='', edge='', kund='', **kwargs)`

Displays results as vectors.

## Parameters

**item**: Predefined vector item (from *PLVECT - Valid Item Labels* below) or a label identifying the i-component of a user-defined vector.

**lab2**: Label identifying the j-component of a user-defined vector. In most cases, this value must be blank if `Item` is selected from *PLVECT - Valid Item Labels*. Individual principal stresses ( `Item` = S) or principal strains ( `Item` = EP `xx` ) may be plotted by specifying the value as 1, 2, or 3.

**lab3**: Label identifying the k-component of a user-defined vector. Must be blank if `Item` is selected from list below or for 2D user defined vector.

**labp**: Label assigned to resultant vector for display labeling (defaults to `Item` ).

**mode**

Vector or raster mode override key:

- `(blank)` - Use the setting of `KEY` on the [[device|/DEVICE]] command.
- `RAST` - Use raster mode for **PLVECT** displays.
- `VECT` - Use vector mode for **PLVECT** displays.

**loc**

Vector location for display of field element results:

- `ELEM` - Display at element centroid (default).
- `NODE` - Display at element nodes.

Nodal results quantities will only be displayed at nodes, not at element centroids.

**edge**

Edge display override key:

- `(blank)` - Use the setting of Key on the [[edge|/EDGE]] command.
- `OFF` - Deactivate the edge display.
- `ON` - Activate the edge display.

**kund**

Undisplaced shape key:

- `0` - Display vectors on undeformed mesh or geometry.
- `1` - Display vectors on deformed mesh or geometry.

## Notes

Displays various solution results as vectors (arrows) for the selected nodes and/or elements (elements must contain at least three nodes that are not colinear). For example, **PLVECT**,U displays the displacement vector for all selected nodes. For section displays ( [[slashtype|/TYPE]] ), the vectors are shown only on the section face (that is, cutting plane). The **PLVECT** display of principal strains and stresses ( `Item` = S, EPTO, EPEL, EPPL, EPCR, or EPTH) on a "cut" of the model ( [[slashtype|/TYPE]],,1,5,7,8, or 9) is not supported. The resulting plot displays the vectors on all selected elements, not on just the sliced surface. See the [[vscale|/VSCALE]] command to scale vector lengths. Vector magnitudes may be shown as a contour display with the [[plnsol|PLNSOL]] command. Various results also depend upon the recalculation method and the selected results location ( [[layer|LAYER]], [[shell|SHELL]], and [[nsel|NSEL]] ).

Items may be selected from a set of recognized vector labels ( `Item` ) or a vector may be defined from up to three scalar labels ( `Item`, `Lab2`, `Lab3` ). Scalar labels may be user-defined with the [[etable|ETABLE]] command. The vectors appear on an element display as arrows showing the relative magnitude of the vector and its direction. The predefined items will be shown either at the node or at the element centroid, depending on what item is being displayed and depending on the `Loc` setting. User defined [[etable|ETABLE]] items will be shown at the element centroid, regardless of the `Loc` setting. Stress vectors appear as arrows at the element centroid, with the arrowheads pointing away from each other for tension and toward each other for compression.

For PowerGraphics, vector arrow displays are generated in Global Cartesian ( [[rsys|RSYS]] = 0). All subsequent displays will revert to your original coordinate system.

When vector mode is active ( `Mode` = VECT), use the Z-buffered display type ( [[slashtype|/TYPE]] ,,6) to maximize speed of **PLVECT** plots (other hidden display types may make plotting slow). For PowerGraphics ( [[graphics|/GRAPHICS]],POWER), the items marked with are not supported by PowerGraphics.

It is possible to plot principal stresses ( `Item` = S) or principal strains ( `Item` = EP `xx` ) individually. To do so, specify a `Lab2` value of 1, 2, or 3. For example, the following are valid commands:

- **PLVECT**,S,1,,,VECT,ELEM,ON,0
- **PLVECT**,EPEL,3,,,VECT,NODE,ON,0

### PLVECT - Valid Item Labels

| Item | Description |
|----|----|
| **Valid item labels for nodal degree of freedom vector results are:** |  |
| U | Structural displacement vector. |
| ROT | Structural rotation vector. |
| V | Velocity vector. |
| A | Magnetic vector potential vector. |
| FFLX | Fluid flux in poromechanics. |
| **Valid item labels for structural element results are:** |  |
| S | Principal stresses \[  \]. |
| EPTO | Principal total strain (EPEL + EPPL + EPCR) \[  \]. |
| EPEL | Principal elastic strains \[  \]. |
| EPPL | Principal plastic strains \[  \]. |
| EPCR | Principal creep strains \[  \]. |
| EPTH | Principal thermal strains \[  \]. |
| EPDI | Principal diffusion strains \[  \]. |
| **Valid item labels for field element results are:** |  |
| TG | Thermal gradient vector. |
| TF | Thermal flux vector. |
| PG | Velocity vector or energy density flux vector (room acoustics). |
| EF | Electric field vector. |
| D | Electric flux density vector. |
| H | Magnetic field intensity vector. If Lab2 is blank, Item is interpreted as one of the predefined labels; otherwise, Item is interpreted as a user-defined [[et\|ET]] label and the program requests a nonblank Lab2 / Lab3 according to the dimension of the problem. |
| B | Magnetic flux density vector. |
| CG | Concentration gradient vector. |
| DF | Diffusion flux density vector. |
| FMAG | Electromagnetic force vector. |
| P | Poynting vector. |
| JS | Source current density vector for low-frequency magnetic analyses. Total current density vector (sum of conduction and displacement current densities) in low frequency electric analyses. |
| JT | Total measurable current density vector in low-frequency electromagnetic analyses. (Conduction current density vector in a low-frequency electric analysis.) |
| JC | Conduction current density vector for elements that support conduction current calculation. |
| SNDI | Sound intensity vector \[  \]. |

Not supported by PowerGraphics

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLVECT.html
