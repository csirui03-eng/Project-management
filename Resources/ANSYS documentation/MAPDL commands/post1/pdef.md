---
apdl: "PDEF"
method: pdef
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.pdef
generated: 2026-08-22
tags: [mapdl-command]
---

# PDEF

PyMAPDL: `mapdl.pdef(lab='', item='', comp='', avglab='', **kwargs)`

Interpolates an item onto a path.

## Parameters

**lab**: Label assigned to the resulting path item (8 characters maximum). This item may be used as input for other path operations.

**item**: Label identifying the item for interpolation. Valid item labels are shown in *PDEF - Valid Item and Component Labels* below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in *PDEF - Valid Item and Component Labels* below.

**avglab**

Option to average across element boundaries:

- `AVG` - Average element results across elements (default).
- `NOAV` - Do not average element results across elements. If the parameter `DISCON` = MAT on the [[pmap|PMAP]] command, this option is automatically invoked.

## Notes

Defines and interpolates a labeled path item along a predefined path ( [[path|PATH]] ). Path item results are in the global Cartesian coordinate directions unless transformed ( [[rsys|RSYS]] ). A path item must be defined before it can be used with other path operations. Additional path items may be defined from the [[pvect|PVECT]], [[pcalc|PCALC]], [[pdot|PDOT]], and [[pcross|PCROSS]] commands. Path items may be listed ( [[prpath|PRPATH]] ) or displayed ( [[plpath|PLPATH]], [[plpagm|PLPAGM]] ). A maximum number of path items permitted is established by the `nSets` argument specified with the [[path|PATH]] command.

When you create the first path item ( **PDEF** or [[pvect|PVECT]] ), the program automatically interpolates four path items which are used to describe the geometry of the path. These predefined items are the position of the interpolated path points (labels XG, YG, and ZG) in global Cartesian coordinates, and the path length (label S). For alternate methods of mapping the path geometry (to include, for example, material discontinuity) see the [[pmap|PMAP]] command. These items may also be listed or displayed with the [[prpath|PRPATH]], [[plpath|PLPATH]], and [[plpagm|PLPAGM]] commands.

If specifying that load case operations act on principal/equivalent stresses ( [[sumtype|SUMTYPE]],PRIN), derived quantities (principal and equivalent stresses/strains) will be zero for path plots. A typical use for such a case involves mode combinations in a response spectrum analysis.

The number of interpolation points on the path is defined by the `nDiv` argument on the [[path|PATH]] command. See [Mapping Nodal and Element Data onto the Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post3.html#LazAk2efjw) **PDEF**,STAT to list the path item labels. Use **PDEF**,CLEAR to erase all labeled path items, except the path geometry items (XG, YG, ZG, S).

See also [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

### PDEF - Valid Item and Component Labels

| Item | Comp | Description |
|----|----|----|
| Valid item and component labels for nodal degree of freedom results are: |  |  |
| U | X, Y, Z, SUM | X, Y, or Z structural displacement or vector sum. |
| ROT | X, Y, Z, SUM | X, Y, or Z structural rotation or vector sum. |
| TEMP\[  \] |  | Temperature. |
| PRES |  | Pressure. |
| VOLT |  | Electric potential. |
| MAG |  | Magnetic scalar potential. |
| V | X, Y, Z, SUM | X, Y, or Z fluid velocity or vector sum. |
| A | X, Y, Z, SUM | X, Y, or Z magnetic vector potential or vector sum. |
| CONC |  | Concentration. |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| Valid item and component labels for element results are: |  |  |
| S | X, Y, Z, XY, YZ, XZ | Component stress. |
| " | 1, 2, 3 | Principal stress. |
| " | INT, EQV | Stress intensity or Equivalent stress. |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total strain (EPEL + EPPL + EPCR). |
| " | 1, 2, 3 | Principal total strain. |
| " | INT, EQV | Total strain intensity or total equivalent strain. |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain. |
| " | 1, 2, 3 | Principal elastic strain. |
| " | INT, EQV | Elastic strain intensity or elastic equivalent strain. |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
| " | 1, 2, 3 | Principal plastic strain. |
| " | INT, EQV | Plastic strain intensity or plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
| " | 1, 2, 3 | Principal creep strain. |
| " | INT, EQV | Creep strain intensity or creep equivalent strain. |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain. |
| " | 1, 2, 3 | Principal thermal strain. |
| " | INT, EQV | Thermal strain intensity or thermal equivalent strain. |
| EPSW |  | Swelling strain. |
| NL | SEPL | Equivalent stress (from stress-strain curve). |
| " | SRAT | Stress state ratio. |
| " | HPRES | Hydrostatic pressure. |
| " | EPEQ | Accumulated equivalent plastic strain. |
| " | PSV | Plastic state variable. |
| " | PLWK | Plastic work/volume. |
| For contact results PowerGraphics is applicable for 3D models only. |  |  |
| CONT | STAT | Contact status. |
| " | PENE | Contact penetration. |
| " | PRES | Contact pressure. |
| " | SFRIC | Contact friction stress. |
| " | STOT | Contact total stress (pressure plus friction). |
| " | SLIDE | Contact sliding distance. |
| " | GAP | Contact gap distance. |
| " | FLUX | Total heat flux at contact surface. |
| TG | X, Y, Z, SUM | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component pressure gradient or vector sum. |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| JC | X, Y, Z, SUM | Component conduction current density or vector sum (for elements that support conduction current calculation) |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum |
| FMAG | X, Y, Z, SUM | Component electromagnetic force or vector sum. |
| ETAB | Lab | Any user-defined element table label (see [[etable\|ETABLE]] command). |
| BFE | TEMP | Applied and calculated temperatures along a defined path. |
| SPL |  | Sound pressure level. |
| SPLA |  | A-weighted sound pressure level (dBA). |

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3,..., TTOP instead of TEMP.

For more information on the meaning of contact status and its possible values, see [Reviewing Results in POST1](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_revresu.html#ctecpostslide)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PDEF.html
