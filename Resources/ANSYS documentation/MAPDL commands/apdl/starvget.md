---
apdl: "*VGET"
method: starvget
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.starvget
generated: 2026-08-22
tags: [mapdl-command]
---

# *VGET

PyMAPDL: `mapdl.starvget(parr='', entity='', entnum='', item1='', it1num='', item2='', it2num='', kloop='', **kwargs)`

Retrieves values and stores them into an array parameter.

## Parameters

**parr**: The name of the resulting vector array parameter. See [[starset|*SET]] for name restrictions. The program creates the array parameter if it does not exist.

**entity**: Entity keyword. Valid keywords are NODE, ELEM, KP, LINE, AREA, VOLU, etc. as shown for `Entity` = in the tables below.

**entnum**: The number of the entity (as shown for `ENTNUM` = in the tables below).

**item1**: The name of a particular item for the given entity. Valid items are as shown in the `Item1` columns of the tables below.

**it1num**: The number (or label) for the specified `Item1` (if any). Valid `IT1NUM` values are as shown in the `IT1NUM` columns of the tables below. Some `Item1` labels do not require an `IT1NUM` value.

**item2**, **it2num**: A second set of item labels and numbers to further qualify the item for which data is to be retrieved. Most items do not require this level of information.

**kloop**

Field to be looped on:

- `0 or 2` - Loop on the `ENTNUM` field (default).
- `3` - Loop on the `Item1` field.
- `4` - Loop on the `IT1NUM` field. Successive items are as shown with `IT1NUM`.
- `5` - Loop on the `Item2` field.
- `6` - Loop on the `IT2NUM` field. Successive items are as shown with `IT2NUM`.

## Notes

### Argument descriptions

- `parr : str` - The name of the resulting vector array parameter. See [[starset|*SET]] for name restrictions. The program creates the array parameter if it does not exist.
- `entity : str` - Entity keyword. Valid keywords are NODE, ELEM, KP, LINE, AREA, VOLU, etc. as shown for `Entity` = in the tables below.
- `entnum : str` - The number of the entity (as shown for `ENTNUM` = in the tables below).
- `item1 : str` - The name of a particular item for the given entity. Valid items are as shown in the `Item1` columns of the tables below.
- `it1num : str` - The number (or label) for the specified `Item1` (if any). Valid `IT1NUM` values are as shown in the `IT1NUM` columns of the tables below. Some `Item1` labels do not require an `IT1NUM` value.
- `item2, it2num : str` - A second set of item labels and numbers to further qualify the item for which data is to be retrieved. Most items do not require this level of information.
- `kloop : str` - Field to be looped on:
  - `0 or 2` - Loop on the `ENTNUM` field (default).
  - `3` - Loop on the `Item1` field.
  - `4` - Loop on the `IT1NUM` field. Successive items are as shown with `IT1NUM`.
  - `5` - Loop on the `Item2` field.
  - `6` - Loop on the `IT2NUM` field. Successive items are as shown with `IT2NUM`.

Retrieves values for specified items and stores the values in an output vector of a user-named array parameter according to: `ParR` = f( `Entity`, `ENTNUM`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM` )

where (f) is the [[get|*GET]] function; `Entity`, `Item1`, and `Item2` are keywords; and `ENTNUM`, `IT1NUM`, and `IT2NUM` are numbers or labels corresponding to the keywords. Looping continues over successive entity numbers ( `ENTNUM` ) for the `KLOOP` default. For example, **\*VGET**,A(1),ELEM,5,CENT,X returns the centroid x-location of element 5 and stores the result in the first location of A. Retrieving continues with element 6, 7, 8, etc., regardless of whether the element exists or is selected, until successive array locations are filled. Use [[vlen|*VLEN]] or [[vmask|*VMASK]] to skip locations. Absolute values and scale factors may be applied to the result parameter ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). See the [[voper|*VOPER]] command for general details. Results can be put back into an analysis by writing a file of the desired input commands with the [[vwrite|*VWRITE]] command. See also the [[starvput|*VPUT]] command.

Both [[get|*GET]] and **\*VGET** retrieve information from the active data stored in memory. The database is often the source, and sometimes the information is retrieved from common memory blocks that Mechanical APDL uses to manipulate information. Although POST1 and POST26 operations use a `\*.rst` file, GET data is accessed from the database or from the common blocks. Get operations do not access the `\*.rst` file directly.

The **\*VGET** command retrieves both the unprocessed real and the imaginary parts (original and duplicate sector nodes and elements) of a [cyclic symmetry](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/cycsym_example.html) solution.

Each of the sections for accessing \*VGET parameters are shown in the following order:

- [\*VGET PREP7 Items](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_VGET_st.html#vget.prep7.tlab) \*VGET PREP7 Items
- [\*VGET POST1 Items](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_VGET_st.html#vget.post1.node.ndof) \*VGET POST1 Items

This command is valid in any processor.

**\*VGET PREP7 Items**

- *\*VGET PREP7 Items, Entity = NODE*
- *\*VGET PREP7 Items, Entity = ELEM*
- *\*VGET PREP7 Items, Entity = KP*
- *\*VGET PREP7 Items, Entity = LINE*
- *\*VGET PREP7 Items, Entity = AREA*
- *\*VGET PREP7 Items, Entity = VOLU*
- *\*VGET PREP7 Items, Entity = CDSY*
- *\*VGET PREP7 Items, Entity = RCON*
- *\*VGET PREP7 Items, Entity = TLAB*

#### \*VGET PREP7 Items, Entity = NODE

`Entity` = NODE, `ENTNUM` = `n` (node number)

**\*VGET**, `ParR`, NODE, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, or Z location in the active coordinate system |
| ANG | XY, YZ, ZX | THXY, THYZ, THZX rotation angle |
| NSEL |  | Select status of node `n` : -1 = unselected, 0 = undefined, 1 = selected |
| NLIST |  | Returns the list of selected nodes ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = ELEM

`Entity` = ELEM, `ENTNUM` = `n` (element number)

**\*VGET**, `ParR`, ELEM, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| NODE | 1, 2,... 20 | Node number at position 1, 2,... 20 of element `n` |
| CENT | X, Y, Z | Centroid X, Y, or Z location (based on shape function) in the active coordinate system |
| ADJ | 1, 2,... 6 | Number of elements adjacent to face 1, 2,... 6 |
| ATTR | `name` | Number assigned to specified attribute; `name` = MAT, TYPE, REAL, ESYS, ENAM, or SECN |
| GEOM |  | Characteristic element geometry. Length of line element (straight line between ends), area of area element, or volume of volume element. Issuing **\*VGET** for an element returns a signed value. To always get a positive value, issue [[vabs\|*VABS]],1 prior to issuing the **\*VGET** command. |
| ESEL |  | Select status of element `n` : -1 = unselected, 0 = undefined, 1 = selected |
| SHPAR | `Test` | Element shape test result for selected element `n`, where `Test` = ASPE (aspect ratio), JACR (Jacobian ratio), MAXA (maximum corner angle), PARA (deviation from parallelism of opposite edges), or WARP (warping factor) |
| ELIST |  | Returns the list of selected elements ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = KP

`Entity` = KP, `ENTNUM` = `n` (keypoint number)

**\*VGET**, `ParR`, KP, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, or Z location in the active coordinate system |
| ATTR | `name` | Number assigned to specified attribute; `name` = MAT, TYPE, REAL, ESYS, NODE, or ELEM |
| DIV |  | Divisions (element size setting) from [[kesize\|KESIZE]] |
| KSEL |  | Select status of keypoint `n` : -1 = unselected, 0 = undefined, 1 = selected |
| KLIST |  | Returns the list of selected keypoints ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = LINE

`Entity` = LINE, `ENTNUM` = `n` (line number)

**\*VGET**, `ParR`, LINE, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| KP | 1, 2 | Keypoint number at position 1 or 2 |
| ATTR | `name` | Number assigned to specified attribute; `name` = MAT, TYPE, REAL, ESYS, NNOD, NELM, or NDIV (NNOD = number of nodes, NELM = number of elements, NDIV = number of divisions) |
| LENG |  | Length |
| LSEL |  | Select status of line `n` : -1 = unselected, 0 = undefined, 1 = selected |
| LLIST |  | Returns the list of selected lines ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = AREA

`Entity` = AREA, `ENTNUM` = `n` (area number)

**\*VGET**, `ParR`, AREA, `n`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `KLOOP`

| Item1 | IT1NUM | Item2 | IT2NUM | Description |
|----|----|----|----|----|
| LOOP | 1,2,... | LINE | 1, 2,... `p` | IT1NUM is the loop number, and must be input if LINE is to be retrieved. IT2NUM is line number at position 1, 2,... `p` |
| ATTR | `name` |  |  | Number assigned to specified attribute; `name` = MAT, TYPE, REAL, ESYS, SECN, NNOD, or NELM (NNOD = number of nodes, NELM = number of elements) |
| AREA | -  |  |  | Area (after last [[asum\|ASUM]] ) |
| ASEL | -  |  |  | Select status of area `n` : -1 = unselected, 0 = undefined, 1 = selected |
| ALIST | -  |  |  | Returns the list of selected areas ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = VOLU

`Entity` = VOLU, `ENTNUM` = `n` (volume number)

**\*VGET**, `ParR`, VOLU, `n`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `KLOOP`

| Item1 | IT1NUM | Item2 | IT2NUM | Description |
|----|----|----|----|----|
| SHELL | 1, 2,... | AREA | 1, 2,... `p` | IT1NUM is the shell number, and must be input if AREA is to be retrieved. IT2NUM is area number at position 1, 2... `p` |
| ATTR | `name` |  |  | Number assigned to specified attribute; `name` = MAT, TYPE, REAL, ESYS, NNOD, or NELM (NNOD = number of nodes, NELM = number of elements) |
| VOLU | -  |  |  | Volume (after last [[vsum\|VSUM]] ) |
| VSEL | -  |  |  | Select status of volume `n` : -1 = unselected, 0 = undefined, 1 = selected |
| VLIST | -  |  |  | Returns the list of selected volumes ( `ENTNUM` is ignored) |

#### \*VGET PREP7 Items, Entity = CDSY

`Entity` = CDSY, `ENTNUM` = `n` (coordinate system number)

**\*VGET**, `ParR`, CDSY, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, or Z origin location (global Cartesian coordinate) |
| ANG | XY, YZ, ZX | THXY, THYZ, or THZX rotation angle (°) relative to the global Cartesian coordinate system |
| ATTR | `name` | Number assigned to specified attribute; `name` = KCS, KTHET, KPHI, PAR1, or PAR2. If the coordinate system is undefined, KCS returns as -1.0 |

#### \*VGET PREP7 Items, Entity = RCON

`Entity` = RCON, `ENTNUM` = `n` (real constant set number)

**\*VGET**, `ParR`, RCON, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM       | Description                                   |
|-------|--------------|-----------------------------------------------|
| CONST | 1, 2,... `m` | Real constant value for constant 1, 2,... `m` |

#### \*VGET PREP7 Items, Entity = TLAB

`Entity` = `TLAB`, `ENTNUM` = `n` ( `TLAB` is the `Lab` data table label on the [[tb|TB]] command. `n` is the material number.)

**\*VGET**, `ParR`, `TLAB`, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Item2 | IT2NUM | Description |
|----|----|----|----|----|
| TEMP | `val` | CONST | `num` | IT1NUM `value` is the temperature value at which to retrieve table data. `num` is the constant number whose value is to be retrieved. For constants input as X, Y points, the constant numbers are consecutive with the X constants being the odd numbers, beginning with one. |

**\*VGET POST1 Items**

- *\*VGET POST1 Items, Entity = CYCCALC*
- *\*VGET POST1 Items, Entity = ELEM*
- *\*VGET POST1 Items, Entity = MEMBER*
- *\*VGET POST1 Items, Entity = NODE, Element Nodal Results*
- *\*VGET POST1 Items, Entity = NODE, Nodal Degree of Freedom Results*

Vector items are in the active results coordinate system unless otherwise specified.

#### \*VGET POST1 Items, Entity = CYCCALC

`Entity` = CYCCALC, `ENTNUM` = `n` ( [[cycspec|CYCSPEC]] specification number)

**\*VGET**, `ParR`, CYCCALC, `n`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `KLOOP`

| Item1 | IT1NUM | Item2 | IT2NUm | Description |
|----|----|----|----|----|
| FREQ | `Frequency point` | SECTOR | `sector` | [[cycspec\|CYCSPEC]] results at the IT1NUM frequency or sector (depending on `KLOOP` ) |
|  |  | SECMAX |  | [[cycspec\|CYCSPEC]] maximum results |
| The frequency point refers to the harmonic solution data set number ( `NSET` on the [[set\|SET]] command). For `KLOOP` = 4 or SECMAX, returns the requested sector results for all frequencies and `IT1NUM` is ignored. For `KLOOP` = 6, returns the requested frequency results for all sectors and `IT2NUM` is ignored. All other `KLOOP` options are invalid. |  |  |  |  |

#### \*VGET POST1 Items, Entity = ELEM

`Entity` = ELEM, `ENTNUM` = `n` (element number)

**\*VGET**, `ParR`, ELEM, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| ETAB | `Label` | Any user-defined element table label (see [[etable\|ETABLE]] command) |

#### \*VGET POST1 Items, Entity = MEMBER

`Entity` = MEMBER, `ENTNUM` = `N` (GroupID)

**\*VGET**, `Par` ,MEMBER, `N`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| TEMP | MIN, MAX | Minimum or maximum temperature of members (individual reinforcings) with GroupID = `N` in the selected set of reinforcing elements |

#### \*VGET POST1 Items, Entity = NODE, Element Nodal Results

`Entity` = NODE, `ENTNUM` = `n` (node number)

**\*VGET**, `ParR`, NODE, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description | Item2 |
|----|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component stress | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
|  | 1, 2, 3 | Principal stress |  |
|  | INT, EQV | Stress intensity or equivalent stress |  |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total strain (EPEL + EPPL + EPCR) |  |
|  | 1, 2, 3 | Principal total strain |  |
|  | INT, EQV | Total strain intensity or total equivalent strain |  |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
|  | 1, 2, 3 | Principal elastic strain |  |
|  | INT, EQV | Elastic strain intensity or elastic equivalent strain |  |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
|  | 1, 2, 3 | Principal plastic strain |  |
|  | INT, EQV | Plastic strain intensity or plastic equivalent strain |  |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
|  | 1, 2, 3 | Principal creep strain |  |
|  | INT, EQV | Creep strain intensity or creep equivalent strain |  |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
|  | 1, 2, 3 | Principal thermal strain |  |
|  | INT, EQV | Thermal strain intensity or thermal equivalent strain |  |
| EPSW |  | Swelling strain | `Item2` controls whether [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used. Valid labels are: AUTO - Use nodal-averaged results, if available. Otherwise use element-based results. ESOL- Use element-based results only. NAR - Use nodal-averaged results only. |
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain |  |
|  | 1, 2, 3 | Principal diffusion strain |  |
|  | INT, EQV | Diffusion strain intensity or diffusion equivalent strain |  |
| NL | SEPL | Equivalent stress (from stress-strain curve) |  |
|  | SRAT | Stress state ratio |  |
|  | HPRES | Hydrostatic pressure |  |
|  | EPEQ | Accumulated equivalent plastic strain |  |
|  | PSV | Plastic state variable |  |
|  | PLWK | Plastic work/volume |  |
| HS | X, Y, Z | Component magnetic field intensity from current sources (in the global Cartesian coordinate system) |  |
| BFE | TEMP | Body temperatures (calculated from applied temperatures) as used in solution |  |
| TG | X, Y, Z, SUM | Component thermal gradient and sum |  |
| TF | X, Y, Z, SUM | Component thermal flux and sum |  |
| PG | X, Y, Z, SUM | Component pressure gradient and sum |  |
| EF | X, Y, Z, SUM | Component electric field and sum |  |
| D | X, Y, Z, SUM | Component electric flux density and sum |  |
| H | X, Y, Z, SUM | Component magnetic field intensity and sum |  |
| B | X, Y, Z, SUM | Component magnetic flux density and sum |  |
| FMAG | X, Y, Z, SUM | Component electromagnetic force and sum |  |
| CONT | STAT | Contact status |  |
|  | PENE | Contact penetration |  |
|  | PRES | Contact pressure |  |
|  | SFRIC | Contact friction stress |  |
|  | STOT | Contact total stress (pressure plus friction) |  |
|  | SLIDE | Contact sliding distance |  |
|  | GAP | Contact gap distance |  |
|  | FLUX | Total heat flux at contact surface |  |
|  | CNOS | Total number of contact status changes during substep |  |
|  | FPRS | Actual applied fluid penetration pressure |  |
| Element nodal results are the average nodal value of the selected elements |  |  |  |

#### \*VGET POST1 Items, Entity = NODE, Nodal Degree of Freedom Results

`Entity` = NODE, `ENTNUM` = `n` (node number)

**\*VGET**, `ParR`, NODE, `n`, `Item1`, `IT1NUM`,, `KLOOP`

| Item1 | IT1NUM | Description |
|----|----|----|
| U | X, Y, Z | X, Y, or Z structural displacement |
| ROT | X, Y, Z | X, Y, or Z structural rotation |
| TEMP |  | Temperature. For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use TBOT, TE2, TE3,..., TTOP instead of TEMP. Alternative get functions: TEMP(N), TBOT(N), TE2(N), etc. |
| PRES |  | Pressure |
| VOLT |  | Electric potential |
| MAG |  | Magnetic scalar potential |
| V | X, Y, Z | X, Y, or Z fluid velocity; X, Y, or Z nodal velocity in a transient structural analysis (analysis with [[antype\|ANTYPE]],TRANS) |
| A | X, Y, Z | X, Y, or Z magnetic vector potential; X, Y or Z nodal acceleration in a transient structural analysis (analysis with [[antype\|ANTYPE]],TRANS) |
| CURR |  | Current |
| EMF |  | Electromotive force drop |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VGET_st.html
