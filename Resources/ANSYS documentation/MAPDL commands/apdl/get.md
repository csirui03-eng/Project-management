---
apdl: "*GET"
method: get
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.get
generated: 2026-08-22
tags: [mapdl-command]
---

# *GET

PyMAPDL: `mapdl.get(par='', entity='', entnum='', item1='', it1num='', item2='', it2num='', **kwargs)`

Retrieves a value and stores it as a scalar parameter or part of an array parameter.

## Parameters

**par**: The name of the resulting parameter. See [[starset|*SET]] for name restrictions.

**entity**: Entity keyword. Valid keywords are NODE, ELEM, KP, LINE, AREA, VOLU, etc., as shown for `Entity` = in the tables below.

**entnum**: The number or label for the entity (as shown for `ENTNUM` = in the tables below). In some cases, a zero (or blank) `ENTNUM` represents all entities of the set.

**item1**: The name of a particular item for the given entity. Valid items are as shown in the `Item1` columns of the tables below.

**it1num**: The number (or label) for the specified `Item1` (if any). Valid `IT1NUM` values are as shown in the `IT1NUM` columns of the tables below. Some `Item1` labels do not require an `IT1NUM` value.

**item2**, **it2num**: A second set of item labels and numbers to further qualify the item for which data are to be retrieved. Most items do not require this level of information.

## Notes

**\*GET** retrieves a value for a specified item and stores the value as a scalar parameter, or as a value in a user-named array parameter. An item is identified by various keyword, label, and number combinations. Usage is similar to the [[starset|*SET]] command except that the parameter values are retrieved from previously input or calculated results.

> Example: **\*GET** Usage
>
> **\*GET**,A,ELEM,5,CENT,X returns the centroid x location of element 5 and stores the result as parameter A.

**\*GET** command operations, and corresponding get functions, return values in the active coordinate system ( [[csys|CSYS]] for input data or [[rsys|RSYS]] for results data) unless stated otherwise.

A get function is an alternative in-line function that can be used instead of the **\*GET** command to retrieve a value. For more information, see.

Both **\*GET** and [[starvget|*VGET]] retrieve information from the active data stored in memory. The database is often the source, and sometimes the information is retrieved from common memory blocks that the program uses to manipulate information. Although POST1 and POST26 operations use a `\*.rst` file, **\*GET** data is accessed from the database or from the common blocks. Get operations do not access the `\*.rst` file directly. For repeated gets of sequential items, such as from a series of elements, see the [[starvget|*VGET]] command.

Most items are stored in the database after they are calculated and are available anytime thereafter. Items are grouped according to where they are usually first defined or calculated. Preprocessing data will often not reflect the calculated values generated from section data. Do not use **\*GET** to obtain data from elements that use calculated section data, such as beams or shells.

When the value retrieved by **\*GET** is a component name, the resulting character parameter is limited to 32 characters. If the component name is longer than 32 characters, the remaining characters are ignored.

Most of the general items listed below are available from all modules. Each of the sections for accessing **\*GET** parameters are shown in the following order:

- *\*GET General Entity Items*
- *\*GET Preprocessing Entity Items*
- *\*GET Solution Entity Items*
- *\*GET Postprocessing Entity Items*

The **\*GET** command is valid in any processor.

**General Items**

### \*GET General Entity Items

- *\*GET General Items, Entity = ACTIVE*
- *\*GET General Items, Entity = CMD*
- *\*GET General Items, Entity = COMP*
- *\*GET General Items, Entity = GRAPH*
- *\*GET General Items, Entity = PARM*
- *\*GET General Items, Entity = TBTYPE*

#### \*GET General Items, Entity = ACTIVE

`Entity` = ACTIVE, `ENTNUM` = 0 (or blank)

**\*GET**, Par, ACTIVE, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| INT |  | Current interactive key: 0=off, 2=on. |
| IMME |  | Current immediate key: 0=off, 1=on. |
| MENU |  | Current menu key: 0=off, 1=on. |
| PRKEY |  | Printout suppression status: 0= [[nopr\|/NOPR]], 1= [[gopr\|/GOPR]] or [[slashgo\|/GO]] |
| UNITS |  | Units specified by [[units\|/UNITS]] command: 0 = USER, 1 = SI, 2 = CGS, 3 = BFT, 4 = BIN, 5 = MKS, 6 = MPA, 7 = uMKS. |
| ROUT |  | Current routine: 0 = Begin level, 17 = PREP7, 21 = SOLUTION, 31 = POST1, 36 = POST26, 52 = AUX2, 53 = AUX3, 62 = AUX12, 65 = AUX15. |
| TIME | WALL,CPU | Current wall clock or CPU time. Current wall clock will continue to accumulate during a run and is not reset to zero at midnight. |
| DBASE | LDATE | Date of first modification of any database quantity required for POST1 operation. The parameter returned is `Par` = YEAR\*10000 + MONTH\*100 + DAY. |
| DBASE | LTIME | Time of last modification of any database quantity required for POST1 operation. The parameter returned is `Par` = HOURS\*10000 + MINUTES\*100 + SECONDS. |
| REV |  | Minor release revision number (5.6, 5.7, 6.0 etc.). Letter notation (for example, 5.0A) is not included. |
| TITLE | 0,1,2,3,4 | **Item2:** START **IT2NUM:** `N` Current title string of the main title ( `IT1NUM` =0 or blank) or subtitle 1, 2, 3, or 4 ( `IT1NUM` =1,2,3, or 4). A character parameter of up to 8 characters, starting at position `N`, is returned. |
| JOBNAM |  | **Item2:** START **IT2NUM:** `N` Current Jobname. A character parameter of up to 8 characters, starting at position `N`, is returned. Use [[dim\|*DIM]] and `*DO` to get all 32 characters. |
| PLATFORM |  | The current platform. |
| NPROC | CURR, MAX, MAXP | The number of processors being used for the current session, or the maximum total number of processors (physical and virtual) available on the machine, or the maximum number of physical processors available on the machine. This only applies to shared-memory parallelism. |
| NUMCPU |  | Number of distributed processes being used (distributed-memory parallel solution). |

#### \*GET General Items, Entity = CMD

`Entity` = CMD, `ENTNUM` = 0 (or blank) The following items are valid for all commands except star (2) commands and non-graphics slash (/) commands.

**\*GET**, `Par`, CMD, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| STAT |  | Status of previous command: 0=found, 1=not found (unknown). |
| NARGS |  | Field number of last nonblank field on the previous command. |
| FIELD | 2,3... `N` | Numerical value of the `N` th field on the previous command. Field 1 is the command name (not available) |

#### \*GET General Items, Entity = COMP

`Entity` = COMP, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, COMP, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                                                  |
|-------|--------|--------------------------------------------------------------|
| NCOMP |        | Total number of components and assemblies currently defined. |

#### \*GET General Items, Entity = GRAPH

`Entity` =GRAPH, `ENTNUM` = N (window number)

**\*GET**, `Par`, GRAPH, N, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ACTIVE |  | [[window\|/WINDOW]] status: 0=off, 1=on. |
| ANGLE |  | [[angle\|/ANGLE]] `THETA` angle. |
| CONTOUR | `Name` | [[contour\|/CONTOUR]] value for `Name`, where `Name` = VMIN, VINC, or NCONT. |
| DIST |  | [[dist\|/DIST]] `DVAL` value. |
| DSCALE | DMULT | [[slashdscale\|/DSCALE]] `DMULT` value. |
| EDGE |  | [[edge\|/EDGE]] `KEY` value. |
| FOCUS | X, Y, Z | [[focus\|/FOCUS]] `CIN`, `YF`, or `ZF` value. |
| GLINE |  | [[gline\|/GLINE]] `STYLE` value. |
| MODE |  | [[user\|/USER]] or [[auto\|/AUTO]] setting: 0=user, 1=auto. |
| NORMAL |  | [[normal\|/NORMAL]] `KEY` value. |
| RANGE | XMIN, XMAX, YMIN, YMAX | [[window\|/WINDOW]] `XMIN`, `XMAX`, `YMIN`, or `YMAX` screen coordinates. |
| RATIO | X, Y | [[ratio\|/RATIO]] `RATOX` or `RATOY` value. |
| SSCALE | SMULT | [[sscale\|/SSCALE]] `SMULT` value. |
| TYPE |  | [[slashtype\|/TYPE]] `Type` value. |
| VCONE | ANGLE | [[vcone\|/VCONE]] `PHI` angle. |
| VIEW | X, Y, Z | [[view\|/VIEW]] `XV`, `YV`, or `ZV` value. |
| VSCALE | VRATIO | [[vscale\|/VSCALE]] `VRATIO` value. |

#### \*GET General Items, Entity = PARM

`Entity` = PARM, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, PARM, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| MAX |  | Total number of parameters currently defined. |
| BASIC |  | Number of scalar parameters (excluding parameters beginning with an underscore \_, array parameters, and character parameters). |
| LOC | `Num` | Name of the parameter at the `Num` location in the parameter table. A character parameter is returned. |

#### \*GET General Items, Entity = TBTYPE

`Entity` = `TBTYPE`, `ENTNUM` = `MatID` (where TBTYPE is the material table type as defined via the [[tb|TB]] command, such (ELASTIC, CTE, etc.), and `MatID` is the material ID) **Evaluates a material property coefficient for a given set of input field variables.**

**\*GET**, `Par`, **TBTYPE**, `MatID`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `Fld1`, `Fld2`,...

| Item1 | IT1NUM | Description |
|----|----|----|
| TBEV: Material table evaluation for query at a given field variable | `SINDEX` = Subtable index (1 - max number of subtables) | **Item2** : `CINDEX` = Coefficient index |
|  |  | **IT2NUM** : `N` = Number of field variables input |
|  |  | `Fld1`, `Fld2`, ..., : `Val` = Value of the field variable(s), entered in the same order specified via the [[tbfield\|TBFIELD]] command(s) |

**Preprocessing Items**

### \*GET Preprocessing Entity Items

- *\*GET Preprocessing Items, Entity = ACTIVE*
- *\*GET Preprocessing items, Entity = AREA*
- *\*GET Preprocessing Items, Entity = AXIS*
- *\*GET Preprocessing Items, Entity = CDSY*
- *\*GET Preprocessing Items, Entity = CE*
- *\*GET Preprocessing Items, Entity = CMPB*
- *\*GET Preprocessing Items, Entity = CP*
- *\*GET Preprocessing Items, Entity = CSEC*
- *\*GET Preprocessing Items, Entity = ELEM*
- *\*GET Preprocessing Items, Entity = ETYP*
- *\*GET Preprocessing Items, Entity = GCN*
- *\*GET Preprocessing Items, Entity = GENB*
- *\*GET Preprocessing Items, Entity = GENS*
- *\*GET Preprocessing Items, Entity = KP*
- *\*GET Preprocessing Items, Entity = LINE*
- *\*GET Preprocessing Items, Entity = LINK*
- *\*GET Preprocessing Items, Entity = MAT*
- *\*GET Preprocessing Items, Entity = MPLAB*
- *\*GET Preprocessing Items, Entity = NODE*
- *\*GET Preprocessing Items, Entity = OCEAN*
- *\*GET Preprocessing Items, Entity = OCZONE*
- *\*GET Preprocessing Items, Entity = PART*
- *\*GET Preprocessing Items, Entity = PIPE*
- *\*GET Preprocessing Items, Entity = RCON*
- *\*GET Preprocessing Items, Entity = REIN*
- *\*GET Preprocessing Items, Entity = SCTN*
- *\*GET Preprocessing Items, Entity = SECP*
- *\*GET Preprocessing Items, Entity = SHEL*
- *\*GET Preprocessing Items, Entity = TBFT*
- *\*GET Preprocessing Items, Entity = TBLAB*
- *\*GET Preprocessing Items, Entity = VOLU*

#### \*GET Preprocessing Items, Entity = ACTIVE

`Entity` = ACTIVE, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, ACTIVE, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| SEG |  | Segment capability of graphics driver: 0=no segments available, 1=erasable segments available, 2=non-erasable segments available. |
| CSYS |  | Active coordinate system. |
| DSYS |  | Active display coordinate system. |
| MAT |  | Active material. |
| TYPE |  | Active element type. |
| REAL |  | Active real constant set. |
| ESYS |  | Active element coordinate system. |
| SECT |  | Active section. |
| CP |  | Maximum coupled node set number in the model (includes merged and deleted sets until compressed out). |
| CE |  | Maximum constraint equation set number in the model (includes merged and deleted sets until compressed out). |

#### \*GET Preprocessing items, Entity = AREA

`Entity` = AREA, `ENTNUM` = `N` (area number)

**\*GET**, `Par`, AREA, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ATTR | `Name` | Number assigned to the attribute, `Name`, where `Name` =MAT, TYPE, REAL, ESYS, KB,KE,SECN, NNOD, NELM, or ESIZ. (NNOD=number of nodes, NELM=number of elements, ESIZ=element size.) |
| ASEL |  | Select status of area `N` : -1=unselected, 0=undefined, 1=selected. Alternative get function: ASEL( `N` ). |
| NXTH |  | Next higher area number above `N` in selected set (or zero if none found). |
| NXTL |  | Next lower area number below `N` in selected set (or zero if none found). |
| AREA |  | Area of area `N`. ( [[asum\|ASUM]] or [[gsum\|GSUM]] must have been performed sometime previously with at least this area `N` selected). |
| LOOP | 1,2,..., `I` | `Item2` : LINE, `IT2NUM` : 1,2,..., `p` Line number of position `p` of loop `I` |

#### \*GET Preprocessing Items, Entity = AXIS

`Entity` = AXIS, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, AXIS, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                     |
|-------|--------|---------------------------------|
| COUNT | \-     | Number of defined sections.     |
| NUM   | MAX    | Largest section number defined. |

#### \*GET Preprocessing Items, Entity = CDSY

`Entity` = CDSY, `ENTNUM` = `N` (coordinate system number)

**\*GET**, `Par`, CDSY, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, or Z origin location in global Cartesian system. |
| ANG | XY, YZ, ZX | THXY, THYZ, or THZX rotation angle (in degrees) relative to the global Cartesian coordinate system. |
| ATTR | `Name` | Number assigned to `Name`, where `Name` =KCS, KTHET, KPHI, PAR1, or PAR2. The value -1.0 is returned for KCS if the coordinate system is undefined. |
| NUM | MAX | The maximum coordinate system number |

#### \*GET Preprocessing Items, Entity = CE

`Entity` = CE, `ENTNUM` = `N` (constraint equation set)

**\*GET**, `Par`, CE, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| If N = 0, then |  |  |
| MAX |  | Maximum constraint equation number |
| NUM |  | Number of constraint equations |
| If N \> 0, then |  |  |
| NTERM |  | Number of terms in this constraint equation |
| CONST |  | Constant term for this constraint equation |
| TERM | number | Item2 = NODE: Gives the node for this position in the constraint equation. Item2 = DOF: Gives the DOF number for this position in the constraint equation. (1-UX, 2-UY, 3-UZ, 4-ROTX, etc.) Item2 = COEF: Gives the coefficient for this position in the constraint equation. |

#### \*GET Preprocessing Items, Entity = CMPB

`Entity` = CMPB, `ENTNUM` = `N` (composite beam section identification number)

**\*GET**, `Par`, CMPB, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| COUNT |  | Number of defined sections. If Item1 = COUNT, then N is blank. |
| NUM | MAX | Largest section number defined. If IT1NUM = MAX, then N is blank. |
| EXIS |  | Returns a 1 if the section exists and if it is a CMPB section. |
| NAME |  | The 8-character section name defined via the [[sectype\|SECTYPE]] command. |
| One of the following: \* CBMX \* CBTE \* CBMD |  | Item2 = NTEM (the number of temperatures for [[cbmx\|CBMX]], [[cbte\|CBTE]], or [[cbmd\|CBMD]] data). |
| One of the following: \* CBMX \* CBTE \* CBMD |  | Item2 = TVAL; IT2NUM = `nnn` where `nnn` is the temperature value (\< = NTEM). |
| One of the following: \* CBMX \* CBTE \* CBMD | `nnn` | Item2 = TEMP; IT2NUM = `tval` Where `nnn` is the location in the [[cbmx\|CBMX]], [[cbte\|CBTE]], or [[cbmd\|CBMD]] command for the given coefficient number, and `tval` is the temperature value. |

#### \*GET Preprocessing Items, Entity = CP

`Entity` = CP, `ENTNUM` = `N` (coupled node set)

**\*GET**, `Par`, CP, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| If N = 0, then |  |  |
| MAX |  | Maximum coupled set number |
| NUM |  | Number of coupled sets |
| If N \> 0, then |  |  |
| DOF |  | The degree of freedom for this set (1-UX, 2-UY, 3-UZ, 4-ROTX, etc.) |
| NTERM |  | Number of nodes in this set. |
| TERM | number | Item2 = NODE: Gives the node for this position number in the coupled set. |

#### \*GET Preprocessing Items, Entity = CSEC

`Entity` = CSEC, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, CSEC, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                     |
|-------|--------|---------------------------------|
| COUNT | \-     | Number of defined sections.     |
| NUM   | MAX    | Largest section number defined. |

#### \*GET Preprocessing Items, Entity = ELEM

`Entity` = ELEM, `ENTNUM` = `N` (element number)

**\*GET**, `Par`, ELEM, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| NODE | 1, 2,... 20 | Node number at position 1,2,... or 20 of element `N`. Alternative get function: NELEM( `n,npos` ), where `npos` is 1,2,...20. |
| CENT | X, Y, Z | Centroid X, Y, or Z location (based on shape function) in the active coordinate system. The original locations is used even if large deflections are active. Alternative get functions: CENTRX( `N` ), CENTRY( `N` ), and CENTRZ( `N` ) always retrieve the element centroid in global Cartesian coordinates, and are determined from the selected nodes on the elements. |
| ADJ | 1, 2,... 6 | Element number adjacent to face 1,2,...6. Alternative get function: ELADJ( `N`, `face` ). Only elements (of the same dimensionality) adjacent to lateral faces are considered. |
| ATTR | `Name` | Number assigned to the attribute `Name`, where `Name` = MAT, TYPE, REAL, ESYS, PSTAT, LIVE, or SECN. Returns a zero if the element is unselected. If `Name` = LIVE, returns a 1 if the element is selected and active, and a -1 if it is selected and inactive. `Name` = SECN returns the section number of the selected beam element. |
| LENG |  | Length of line element (straight line between ends). |
| LPROJ | X, Y, Z | Projected line element length (in the active coordinate system). X is x-projection onto y-z plane, Y is y projection onto z-x plane, and Z is z-projection onto x-y plane. |
| AREA |  | Area of area element. |
| APROJ | X, Y, Z | Projected area of area element area (in the active coordinate system). X is x-projection onto y-z plane, Y is y projection onto z-x plane, and Z is z-projection onto x-y plane. |
| VOLU |  | Element volume. Based on unit thickness for 2D plane elements (unless the thickness option is used) and on the full 360 degrees for 2D axisymmetric elements. For general axisymmetric elements `SOLID272` and `SOLID273`, only the area of the element on the master plane is reported before solving, not the volume. After solving, the volume is reported. If results data are in the database, the volume returned is the volume calculated during solution. |
| ESEL |  | Select status of element `N` : -1 = unselected, 0 = undefined, 1 = selected. Alternative get function: ESEL( `N` ). |
| NXTH |  | Next higher element number above `N` in selected set (or zero if none found). Alternative get function: ELNEXT( `N` ) |
| NXTL |  | Next lower element number below `N` in selected set (or zero if none found). |
| HGEN |  | Heat generation on selected element `N`. |
| DGEN |  | Diffusing substance generation on selected node N (returns 0.0 if node is unselected, or if the DOF is inactive). |
| HCOE | face | Heat coefficient for selected element `N` on specified face. Returns the value at the first node that forms the face. |
| TBULK | face | Bulk temperature for selected element `N` on specified face. Returns the value at the first node that forms the face. |
| PRES | face | Pressure on selected element, `N` on specified face. Returns the value at the first node that forms the face. |
| SHPAR | `Test` | Element shape test result for selected element `N`, where `Test` = ANGD, ASPE (aspect ratio), JACR (Jacobian ratio), MAXA (maximum corner angle), PARA (deviation from parallelism of opposite edges), or WARP (warping factor). |
| MEMBER | COUNT | Number of reinforcing members (individual reinforcings) in the element `N`. |
| EGID | COUNT | Number of non-duplicate global identifiers in the element `N`. |
|  | MIN, MAX | Lowest or highest global identifier in the element `N`. |

#### \*GET Preprocessing Items, Entity = ETYP

`Entity` = ETYP, `ENTNUM` = `N` (element type number)

**\*GET**, `Par`, ETYP, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ATTR | `Name` | Number assigned to the attribute `Name`, where `Name` =ENAM, KOP1, KOP2,..., KOP9, KO10, KO11, etc. |

#### \*GET Preprocessing Items, Entity = GCN

`Entity` = GCN, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, GCN, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| MAT | `Sect1` | `Item2` = 0 or blank; `IT2NUM` = `Sect2`. Material ID to be used for general contact between `Sect1` and `Sect2`. Alternative get function: SECTOMAT( `Sect1`, `Sect2` ). |
| REAL | `Sect1` | `Item2` = 0 or blank; `IT2NUM` = `Sect2`. Real constant ID to be used for general contact between `Sect1` and `Sect2`. Alternative get function: SECTOREAL( `Sect1`, `Sect2` ). |
| DEF | `Sect1` | `Item2` = 0 or blank; `IT2NUM` = `Sect2`. Number indicating the type of contact for the general contact definition between `Sect1` and `Sect2` : \* = 0 - Excluded general contact between `Sect1` / `Sect2` \* = 1 - Asymmetric general contact between `Sect1` (contact) / `Sect2` (target) \* = 2 - Asymmetric general contact between `Sect1` (target) / `Sect2` (contact) \* = 3 - Symmetric general contact between `Sect1` / `Sect2` |
| `Sect1` and `Sect2` are section numbers associated with general contact surfaces. |  |  |

#### \*GET Preprocessing Items, Entity = GENB

`Entity` = GENB, `ENTNUM` = `N` (nonlinear beam general section identification number)

**\*GET**, `Par`, GENB, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| COUNT | (Blank) | Number of defined sections. If `Item1` = COUNT, then `N` is blank. |
| NUM | MAX | Largest section number defined. If `IT1NUM` = MAX, then `N` is blank. |
| EXIS | (Blank) | Returns a 1 if the section exists and if it is a GENB section. |
| SUBTYPE | (Blank) | Section subtype for the section ID specified via the [[sectype\|SECTYPE]] command. |
| NAME | (Blank) | The 8-character section name defined via the [[sectype\|SECTYPE]] command. |
| One of the following: \* BSAX \* BSM1 \* BSM2 \* BSTQ \* BSS1 \* BSS2 \* BSMD \* BSTE | (Blank) | `Item2` = NTEM, the number of temperatures for [[bsax\|BSAX]], [[bsm1\|BSM1]], [[bsm2\|BSM2]], [[bstq\|BSTQ]], [[bss1\|BSS1]], [[bss2\|BSS2]], [[bsmd\|BSMD]], or [[bste\|BSTE]] data. |
| One of the following: \* BSAX \* BSM1 \* BSM2 \* BSTQ \* BSS1 \* BSS2 \* BSMD \* BSTE | (Blank) | `Item2` = TVAL; `IT2NUM` = `nnn` Where `nnn` is the temperature value (\<= NTEM). |
| One of the following: \* BSAX \* BSM1 \* BSM2 \* BSTQ \* BSS1 \* BSS2 \* BSMD \* BSTE | `nnn` | `Item2` = TEMP; `IT2NUM` = `tval` Where `nnn` is the location in the [[bsax\|BSAX]], [[bsm1\|BSM1]], [[bsm2\|BSM2]], [[bstq\|BSTQ]], [[bss1\|BSS1]], [[bss2\|BSS2]], [[bsmd\|BSMD]], or [[bste\|BSTE]] command for the given coefficient number, and `tval` is the temperature value. Examples for `nnn` : \* `nnn` = 1 for STRAIN(1) \* `nnn` = 2 for STRESS(1) \* `nnn` = 3 for STRAIN(2) \* `nnn` = 4 for STRESS(2) \* `nnn` = 5 for STRAIN(3) \*... |
| One of the following: \* BSAX \* BSM1 \* BSM2 \* BSTQ \* BSS1 \* BSS2 \* BSMD \* BSTE | (Blank) | `Item2` = TEMP; `IT2NUM` = `tval` ; `Item3` = NCONST The number of constants at `tval`. |

#### \*GET Preprocessing Items, Entity = GENS

`Entity` = GENS, `ENTNUM` = `N` (preintegrated shell general section identification number)

**\*GET**, `Par`, GENS, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| COUNT | (Blank) | Number of defined sections. If `Item1` = COUNT, then `N` is blank. |
| NUM | MAX | Largest section number defined. If `IT1NUM` = MAX, then `N` is blank. |
| EXIS | (Blank) | Returns a 1 if the section exists and if it is a GENS section. |
| NAME | (Blank) | The 8-character section name defined via the [[sectype\|SECTYPE]] command. |
| One of the following: \* SSPA \* SSPB \* SSPD \* SSPE \* SSMT \* SSBT \* SSPM | (Blank) | `Item2` = NTEM, the number of temperatures for [[sspa\|SSPA]], [[sspb\|SSPB]], [[sspd\|SSPD]], [[sspe\|SSPE]], [[ssmt\|SSMT]], [[ssbt\|SSBT]], or [[sspm\|SSPM]] data. |
| One of the following: \* SSPA \* SSPB \* SSPD \* SSPE \* SSMT \* SSBT \* SSPM | (Blank) | `Item2` = TVAL; `IT2NUM` = `nnn` Where `nnn` is the temperature value (\<= NTEM). |
| One of the following: \* SSPA \* SSPB \* SSPD \* SSPE \* SSMT \* SSBT \* SSPM | `nnn` | `Item2` = TEMP; `IT2NUM` = `tval` Where `nnn` is the location in the [[sspa\|SSPA]], [[sspb\|SSPB]], [[sspd\|SSPD]], [[sspe\|SSPE]], [[ssmt\|SSMT]], [[ssbt\|SSBT]], or [[sspm\|SSPM]] command for the given coefficient number, and `tval` is the temperature value. |

#### \*GET Preprocessing Items, Entity = KP

`Entity` = KP, `ENTNUM` = `N` (keypoint number)

**\*GET**, `Par`, KP, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, or Z location in the active coordinate system. Alternative get functions: KX( `N` ), KY( `N` ), KZ( `N` ). Inverse get function: KP( `x,y,z` ) returns the number of the selected keypoint nearest the `x,y,z` location (in the active coordinate system, lowest number for coincident keypoints). |
| ATTR | `Name` | Number assigned to the attribute `Name`, where `Name` = MAT, TYPE, REAL, ESYS, NODE, or ELEM. |
| KSEL |  | Select status of keypoint `N` : -1 = unselected, 0 = undefined, 1 = selected. Alternative get function: KSEL( `N` ). |
| NXTH |  | Next higher keypoint number above `N` in selected set (or zero if none found). Alternative get function: KPNEXT( `N` ). |
| NXTL |  | Next lower keypoint number below `N` in selected set (or zero if none found). |
| DIV |  | Divisions (element size setting) from [[kesize\|KESIZE]] command. |

#### \*GET Preprocessing Items, Entity = LINE

`Entity` = LINE, `ENTNUM` = `N` (line number)

**\*GET**, `Par`, LINE, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| KP | 1,2 | Keypoint number at position 1 or 2. |
| ATTR | `Name` | Number assigned to the attribute, `Name`, where `Name` =MAT, TYPE, REAL, ESYS, NNOD, NELM, NDIV, NDNX, SPAC, SPNX, KYND, KYSP, LAY1, or LAY2. (NNOD=number of nodes, returns -1 for meshed line with no internal nodes, NELM=number of elements, NDIV=number of divisions in an existing mesh, NDNX=number of divisions assigned for next mesh, SPAC=spacing ratio in an existing mesh, SPNX=spacing ratio for next mesh, KYND=soft key for NDNX, KYSP=soft key for SPNX, LAY1=LAYER1 setting, LAY2=LAYER2 setting.) |
| LSEL |  | Select status of line `N` : -1=unselected, 0=undefined, 1=selected. Alternative get function: LSEL( `N` ). |
| NXTH |  | Next higher line number above `N` in the selected set (or zero if none found). Alternative get function: LSNEXT( `N` ) |
| NXTL |  | Next lower line number below `N` in selected set (or zero if none found). |
| LENG |  | Length. A get function LX( `n,lfrac` ) also exists to return the X coordinate location of line `N` at the length fraction `lfrac` (0.0 to 1.0). Similar LY and LZ functions exist. |

#### \*GET Preprocessing Items, Entity = LINK

`Entity` = LINK, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, LINK, `NUM`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                     |
|-------|--------|---------------------------------|
| COUNT |        | Number of defined sections.     |
| NUM   | MAX    | Largest section number defined. |

#### \*GET Preprocessing Items, Entity = MAT

`Entity` = MAT, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, MAT, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| COUNT |  | Number of materials. |
| NUM | MAX | Largest material number for which at least one property is defined. |

#### \*GET Preprocessing Items, Entity = MPLAB

`Entity` = MPlab, `ENTNUM` = `N` ( `MPlab` = material property label from [[mp|MP]] command; `N` = material number.)

**\*GET**, `Par`, MPlab, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| TEMP | val | Material property value at temperature of `val` . For temperature dependent materials, the program interpolates the property at temperature input for `val`. |

#### \*GET Preprocessing Items, Entity = NODE

`Entity` = NODE, `ENTNUM` = `N` (node number)

**\*GET**, `Par`, NODE, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| LOC | X, Y, Z | X, Y, Z location in the active coordinate system. Alternative get functions: NX( `N` ), NY( `N` ), NZ( `N` ). Inverse get function. NODE( `x,y,z` ) returns the number of the selected node nearest the `x,y,z` location (in the active coordinate system, lowest number for coincident nodes). |
| ANG | XY, YZ, ZX | THXY, THYZ, THZX rotation angle. |
| NSEL |  | Select status of node `N` : -1=unselected, 0=undefined, 1=selected. Alternative get function: NSEL( `N` ). |
| NXTH |  | Next higher node number above `N` in selected set (or zero if none found). Alternative get function: NDNEXT( `N` ). |
| NXTL |  | Next lower node number below `N` in selected set (or zero if none found). |
| F | FX, MX,... | Applied force at selected node `N` in direction `IT1NUM` (returns 0.0 if no force is defined, if node is unselected, or if the DOF is inactive). If `ITEM2` is IMAG, return the imaginary part. |
| D | UX, ROTX,... | Applied constraint force at selected node `N` in direction `IT1NUM` (returns a large number, such as 2e100, if no constraint is specified, if the node is unselected, or if the DOF is inactive). If `ITEM2` is IMAG, return the imaginary part. |
| HGEN |  | Heat generation on selected node `N` (returns 0.0 if node is unselected, or if the DOF is inactive). |
| NTEMP |  | Temperature on selected node N (returns 0.0 if node is unselected) |
| CPS | Lab | Couple set number with direction Lab = any active DOF, which contains the node `N`. |
| DGEN |  | Diffusing substance generation on selected node N (returns 0.0 if node is unselected, or if the DOF is inactive). |

#### \*GET Preprocessing Items, Entity = OCEAN

`Entity` = OCEAN, `ENTNUM` = `Type` (where `Type` is a valid label on the `DataType` field of the [[octype|OCTYPE]] command)

**\*GET**, `Par`, OCEAN, `Type`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| NAME |  | Name defined for a given `Type` |
| DATA | 1 | Depth when `Type` = BASI |
|  | 2 | Material ID when `Type` = BASI |
|  | 8 | `KFLOOD` when `Type` = BASI |
|  | 9 | `Cay` when `Type` = BASI |
|  | 10 | `Cb` when `Type` = BASI |
|  | 11 | `Zmsl` when `Type` = BASI |
|  | 13 | `Caz` when `Type` = BASI |
|  | 14 | `Ktable` when `Type` = BASI |
|  | 1 | `KWAVE` when `Type` = WAVE |
|  | 2 | `THETA` when `Type` = WAVE |
|  | 3 | `WAVELOC` when `Type` = WAVE |
|  | 4 | `KCRC` when `Type` = WAVE |
|  | 5 | `KMF` when `Type` = WAVE |
|  | 6 | `PRKEY` when `Type` = WAVE |
| PROP | NROW | Number of rows defined by [[octable\|OCTABLE]] command |
| TABL | `i` | Data in table defined by [[octable\|OCTABLE]] command `i` = row number; Item2 = column number |

(table not available in the PyMAPDL source, see the Ansys help page)

#### \*GET Preprocessing Items, Entity = OCZONE

`Entity` = OCZONE, `ENTNUM` = `Name` (where `Name` is a valid label on the `ZoneName` field of the [[oczone|OCZONE]] command)

**\*GET**, `Par`, OCZONE, `Name`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| DATA | 8 | `KFLOOD` for a given `ENTNUM` = `Name` |
|  | 9 | `Cay` for a given `ENTNUM` = `Name` |
|  | 10 | `Cb` for a given `ENTNUM` = `Name` |
|  | 13 | `Caz` for a given `ENTNUM` = `Name` |
| PROP | NROW | Number of rows defined by [[octable\|OCTABLE]] command |
| TABL | `i` | Data in table defined by [[octable\|OCTABLE]] command `i` = row number; Item2 = column number |
| TYPE |  | Ocean zone type (returns 1, 2 or 3 for ZLOC-, COMP-, or PIP-type zones, respectively) |
| COMP |  | Component name when the given ocean zone type is COMP, or internal component name when the given ocean zone type is PIP |
| COMP2 |  | External component name when the type of given ocean zone is PIP |

(table not available in the PyMAPDL source, see the Ansys help page)

(table not available in the PyMAPDL source, see the Ansys help page)

#### \*GET Preprocessing Items, Entity = PIPE

`Entity` = PIPE, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, PIPE, `NUM`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                    |
|-------|--------|--------------------------------|
| COUNT |        | Number of defined sections     |
| NUM   | MAX    | Largest section number defined |

#### \*GET Preprocessing Items, Entity = PART

`Entity` = PART, `ENTNUM` = `N` (PART number)

**\*GET**, `Par`, PART, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                                |
|-------|--------|--------------------------------------------|
| TYPE  |        | Element type number assigned to PART `N`.  |
| MAT   |        | Material number assigned to PART `N`.      |
| REAL  |        | Real constant number assigned to PART `N`. |

#### \*GET Preprocessing Items, Entity = RCON

`Entity` = [[rcon|RCON]], `ENTNUM` = `N` (real constant set number)

| **\*GET**, `Par`, RCON, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM` |  |  |
|----|----|----|
| CONST | 1, 2,..., `m` | Value of real constant number `m` in set `N`. |
| **\*GET** | \[\*GET ,Par, RCON,0, Item1, IT1NUM, Item2, IT2NUM\] |  |
| NUM | MAX | The maximum real constant set number defined |

#### \*GET Preprocessing Items, Entity = REIN

`Entity` = REIN, `ENTNUM` = `N` (reinforcing section identification number)

**\*GET**, `Par`, REIN, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| TYPE |  | Section type, for ID - [[sectype\|SECTYPE]] command (always REIN for reinforcing sections). |
| SUBTYPE |  | Section subtype for ID - [[sectype\|SECTYPE]] command. |
| NAME |  | Name defined for a given ID number. |
| NREIN |  | Number of reinforcing fibers. For reinforcing sections generated ( [[ereinf\|EREINF]] ) via the standard method, the number of fibers defined via [[secdata\|SECDATA]]. For reinforcing sections generated ( [[ereinf\|EREINF]] ) via the mesh-independent method, the total number of fibers in the section. |
| TABL | `ReinfNum,I` | Reinforcing fiber data, as defined via [[secdata\|SECDATA]]. This item is not allowed for reinforcing sections generated ( [[ereinf\|EREINF]] ) via the mesh-independent method. |

#### \*GET Preprocessing Items, Entity = SCTN

`Entity` = SCTN, `ENTNUM` = `N` (pretension section ID number)

**\*GET**, `Par`, SCTN, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| 1 |  | Section ID number. |
| 2 |  | Section type (always 5 for pretension section). |
| 3 |  | Pretension node number. |
| 4 | Coordinate system number. | Section normal NX. |
| 5 | Coordinate system number. | Section normal NY. |
| 6 | Coordinate system number. | Section normal NZ. |
| 7 or 8 |  | Eight character section name. |
| 9 |  | Initial action key. Returns 0 or 1 for lock, 2 for "free-to-slide," or 3 for tiny. |
| 10 |  | Force displacement key. Returns 0 or 1 for force, or 2 for displacement. |
| 11 |  | First preload value. |
| 12 |  | Load step in which first preload value is to be applied. |
| 13 |  | Load step in which first preload value is to be locked. |
| 14... |  | 14 through 17 is a repeat of 10 through 13, but for the second preload value; 18 through 21 is for the third preload value; and so forth. |

#### \*GET Preprocessing Items, Entity = SECP

`Entity` = SECP, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, SECP, `NUM`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description                    |
|-------|--------|--------------------------------|
| COUNT |        | Number of defined sections     |
| NUM   | MAX    | Largest section number defined |

#### \*GET Preprocessing Items, Entity = SHEL

`Entity` = SHEL, ENTNUM = `N` (shell section identification number)

**\*GET**, `Par`, SHEL, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| TYPE |  | Section type, for id - [[sectype\|SECTYPE]] command. (always SHEL for shell sections) |
| NAME |  | Name defined for a given id number. |
| PROP | TTHK | Total thickness. |
|  | NLAY | Number of layers. |
|  | NSP | Number of section integration points. |
|  | POS | Node position (as defined by [[secoffset\|SECOFFSET]] ). |
|  |  | 0 = User Defined. |
|  |  | 1 = Middle. |
|  |  | 2 = Top. |
|  |  | 3 = Bottom. |
|  | OFFZ | User-defined section offset (POS = 0). |
|  | TS11 | Transverse shear stiffness factors. |
|  | TS22 | Transverse shear stiffness factors. |
|  | TS12 | Transverse shear stiffness factors. |
|  | HORC | Homogeneous or complete section flag. |
|  |  | 0 = Homogeneous. |
|  |  | 1 = Composite. |
|  | FUNC | Tabular function name for total thickness. |
|  | UT11 | User transverse shear stiffness 11. |
|  | UT22 | User transverse shear stiffness 22. |
|  | UT12 | User transverse shear stiffness 12. |
|  | AMAS | Added mass. |
|  | MSCF | Hourglass control membrane scale factor. |
|  | BSCF | Hourglass control bending scale factor. |
|  | DSTF | Drill stiffness scale factor. |
|  | LDEN | Laminate density. |
|  | FKCN | `KCN` field value from the [[secfunction\|SECFUNCTION]] command, in which the array or table is interpreted. |
|  | ABD | Section membrane and bending stiffness matrix. Valid ITEM2 = 1,6 and IT2NUM = 1,6. |
|  | E | Section transverse shear stiffness matrix. Valid ITEM2 = 1,2 and IT2NUM = 1,2. |
| LAYD | LayerNumber,THIC | Layer thickness. |
|  | LayerNumber,MAT | Layer material. |
|  | LayerNumber,ANGL | Layer orientation angle. |
|  | LayerNumber,NINT | Number of layer integration points. |

#### \*GET Preprocessing Items, Entity = TBFT

`Entity` = TBFT, `ENTNUM` = `blank`

**\*GET**, `Par`, TBFT, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| nmat |  | Number of defined material models. |
| matnum | `index` | Material number in array (index varies for 1 to num materials). |
| `Entity` = TBFT, `ENTNUM` = `matid` (For getting names of constitutive function, matid = the material ID number) |  |  |
| **\*GET** | \[\*GET ,Par, TBFT,matid,nfun,IT1NUM,Item2,IT2NUM\] |  |
| Item1 | IT1NUM | Description |
| nfun |  | Number of constitutive functions for this material. |
| `Entity` = TBFT, `ENTNUM` = `matid` (To query constitutive function data, matid = the material ID number) |  |  |
| **\*GET** | \[\*GET ,Par, TBFT,matid,func,fname,Item2,IT2NUM\] |  |
| Item1 | IT1NUM | Description |
| func | index | If Item2 = fname, the name of the constitutive function is returned. |
| func | function name | If Item2 = ncon, the number of constants is returned for the function specified in IT1NUM by the constitutive function name. |
| " | " | If Item2 = cons, set Item2num to index to return the value of the constant. |
| " | " | If Item2 = fixe, set Item2num to index to return the fix flag status. |
| " | " | If Item2 = RESI, returns the residual error while fitting the data. |
| " | " | If Item2 = type, returns the category of the constitutive model (moon, poly, etc.) |
| " | " | If Item2 = sord, returns the shear order of the prony visco model. |
| " | " | If Item2 = bord, returns the bulk order of the prony visco model. |
| " | " | If Item2 = shif, returns the shift function name of the prony visco model. |
| `Entity` = TBFT, `ENTNUM` = `matid` (For getting names of experimental data, matid = the material ID number) |  |  |
| **\*GET** | \[\*GET ,Par, TBFT,matid,nexp,IT1NUM,Item2,IT2NUM\] |  |
| Item1 | IT1NUM | Description |
| nexp |  | Number of experiments for this material. |
| `Entity` = TBFT, `ENTNUM` = `matid` (To query experimental data, `matid` = the material ID number)) |  |  |
| **\*GET** | \[\*GET ,Par, TBFT,matid,func,fname,Item2,IT2NUM\] |  |
| Item1 | IT1NUM | Description |
| " | expindex | If Item2 = type, returns experiments type string. |
| " | " | If Item2 = numrow, returns number of rows in the data. |
| " | " | If Item2 = numcol, returns the number of cols in a row (set Intem2num = Row index) |
| " | " | If Item2 = data, returns the value of the data in row, col of exp expindex (set item2Num = row index and item3 = column index. All indices vary from 1 to the maximum value. |
| " | " | If Item2 = natt, returns the number of attributes. |
| " | " | If Item2 = attname, returns the attribute name (set Item2Num = Attr index). |
| " | " | If Item2 = attvald, returns double value of attribute (set Item2Num = Attr index). |
| " | " | If Item2 = attvali, returns integer valud of attribute (set Item2Num = Attr index). |
| " | " | If Item2 = attvals, returns the string value of the attribute (set Item2Num = Attr index). |

#### \*GET Preprocessing Items, Entity = TBLAB

`Entity` = TBLAB, `ENTNUM` = `N` ..( `TBlab` = data table label from the [[tb|TB]] command; `N` = material number.)

**\*GET**, `Par`, `TBlab`, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `TBOPT`

| Item1 | IT1NUM | Description |
|----|----|----|
| TEMP | `T` | **Item2** : CONST **IT2NUM** : `Num` Value of constant number Num in the data table at temperature `T`. For constants, input an X,Y point; the constant numbers are consecutive with the X constants being the odd numbers, beginning with one. |
| To get all necessary output for materials defined via the [[tb\|TB]] command, you must specify the final argument `TBOPT` as indicated in the syntax description above. |  |  |

#### \*GET Preprocessing Items, Entity = VOLU

`Entity` = VOLU, `ENTNUM` = `N` (volume number)

**\*GET**, `Par`, VOLU, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ATTR | `Name` | Number assigned to the attribute `Name`, where `Name` =MAT, TYPE, REAL, ESYS, NNOD, or NELM. (NNOD=number of nodes, NELM=number of elements.) |
| VSEL |  | Select status of volume `N` : -1=unselected, 0=undefined, 1=selected. Alternative get function: VSEL( `N` ). |
| NXTH |  | Next higher volume number above `N` in selected set (or zero if none found). Alternative get function: VLNEXT( `N` ). |
| NXTL |  | Next lower volume number below `N` in selected set (or zero if none found). |
| VOLU |  | Volume of volume `N`. ( [[vsum\|VSUM]] or [[gsum\|GSUM]] must have been performed sometime previously with at least this volume `N` selected). |
| SHELL | 1, 2,..., `m` | **Item2** : AREA **IT2NUM** : 1,2,..., `p` Line number of position `p` of shell `m` |

**Solution Items**

### \*GET Solution Entity Items

- *\*GET Solution Items, Entity = ACTIVE*
- *\*GET Solution Items, Entity = ELEM*
- *\*GET Solution Items, Entity = MODE*
- *\*GET Solution Items, Entity = DDAM*

#### \*GET Solution Items, Entity = ACTIVE

`Entity` = ACTIVE, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, ACTIVE, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ANTY |  | Current analysis type. |
| SOLU | DTIME | Time step size. |
|  | NCMLS | Cumulative number of load steps. |
|  | NCMSS | Number of substeps. NOTE: Used only for static and transient analyses. |
|  | EQIT | Number of equilibrium iterations. |
|  | NCMIT | Cumulative number of iterations. |
|  | CNVG | Convergence indicator: 0=not converged, 1=converged. |
|  | MXDVL | Maximum degree of freedom value. |
|  | RESFRQ | Response frequency for 2nd order systems. |
|  | RESEIG | Response eigenvalue for 1st order systems. |
|  | DSPRM | Descent parameter. |
|  | FOCV | Force convergence value. |
|  | MOCV | Moment convergence value. |
|  | HFCV | Heat flow convergence value. |
|  | MFCV | Magnetic flux convergence value. |
|  | CSCV | Current segment convergence value. |
|  | CUCV | Current convergence value. |
|  | FFCV | Fluid flow convergence value. |
|  | DICV | Displacement convergence value. |
|  | ROCV | Rotation convergence value. |
|  | TECV | Temperature convergence value. |
|  | VMCV | Vector magnetic potential convergence value. |
|  | SMCV | Scalar magnetic potential convergence value. |
|  | VOCV | Voltage convergence value. |
|  | PRCV | Pressure convergence value. |
|  | VECV | Velocity convergence value. |
|  | CRPRAT | Maximum creep ratio. |
|  | PSINC | Maximum plastic strain increment. |
|  | CGITER | Number of iterations in the PCG and symmetric JCG (non-complex version) solvers. |

#### \*GET Solution Items, Entity = ELEM

`Entity` = ELEM, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, ELEM, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM              | Description                                      |
|-------|---------------------|--------------------------------------------------|
| MTOT  | X, Y, Z             | Total mass components.                           |
| MC    | X, Y, Z             | Center of mass components.                       |
| IOR   | X, Y, Z, XY, YZ, ZX | Moment of inertia about origin.                  |
| IMC   | X, Y, Z, XY, YZ, ZX | Moment of inertia about the center of mass.      |
| IPRIN | X, Y, Z             | Principal moments of inertia.                    |
| IANG  | XY, YZ, ZX          | Angles of the moments of inertia principal axes. |
| FMC   | X, Y, Z             | Force components at mass centroid ( 1).          |
| MMOR  | X, Y, Z             | Moment components at origin (                    |
| MMMC  | X, Y, Z             | Moment components at mass centroid (             |

Items ( 1) are available only after inertia relief solution ( [[irlf|IRLF]],1) or pre-calculation of masses ( [[irlf|IRLF]],-1).

> Item values are consistent with the mass summary printed in the output file. They are based on

unscaled mass properties (see [[mascale|MASCALE]] command).

#### \*GET Solution Items, Entity = MODE

`Entity` = MODE, `ENTNUM` = `N` (mode number)

**\*GET**, `Par`, MODE, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| FREQ |  | Frequency of mode `N`. Returned values are valid for modal analyses which calculate real eigensolutions. |
| STAB |  | Stability value of mode `N`. Returned values are valid for modal analyses which calculate complex eigensolutions. The stability value is the real part of the complex eigenvalue. It contains information on the mode damping in a damped modal analysis. |
| DFRQ |  | Damped frequency of mode `N`. Returned values are valid for modal analyses which calculate complex eigensolutions. The damped frequency is the imaginary part of the complex eigenvalue. |
| PFACT |  | Participation factor of mode `N`. \* If retrieved after a modal analysis, the real part of the participation factor is returned unless `IT1NUM` = IMAG. The direction is specified using `Item2` = DIREC and `IT2NUM` = X, Y, Z, ROTX, ROTY, or ROTZ \* If retrieved after a spectrum analysis, the spectrum number M is specified using `Item2` = SPECT and `IT2NUM` = M. For a PSD analysis with spatial correlation or wave excitation, the retrieved participation factors will correspond to the first degree of freedom that is excited. |
| EFFM |  | Effective mass of mode `N`. Returned values are valid only after a modal analysis with effective mass calculation has been solved. The direction is specified using `Item2` = DIREC and `IT2NUM` = X, Y, Z, ROTX, ROTY, or ROTZ. |
| GENM |  | Generalized mass (also called modal mass) of mode `N`. Returned values are valid only after a modal analysis with generalized mass calculation has been solved. |
| MCOEF |  | Mode coefficient of mode `N`. Returned values are valid only after a spectrum analysis has been solved. The spectrum number M is specified using `Item2` = SPECT and `IT2NUM` = M. In a SPRS analysis, the values returned are based on the curve with the lowest damping. After a PSD analysis, the diagonal of the dynamic modal covariance matrix is retrieved for the displacement solution. |
| DAMP |  | Damping ratio of mode `N`. If retrieved after a modal analysis that creates complex solutions (DAMP, QRDAMP, or UNSYM eigensolvers) returned value is calculated from the complex frequencies. If retrieved after a spectrum analysis, returned value is the effective damping ratio. Not a function of direction. Also retrievable following a harmonic analysis or transient analysis with mode-superposition. |

For all items except PFACT and MCOEF (as noted above), only the first 10000 values corresponding to significant modes will be returned.

The MODE file must be available to retrieve items PFACT and MCOEF with specified `Item2`. If `Item2` is not specified, the last calculated value will be returned.

All values retrieved correspond to the first load step values. For a Campbell diagram analysis (multistep modal), **\*GET** with `Entity` = CAMP must be used.

#### \*GET Solution Items, Entity = DDAM

`Entity` = DDAM, `ENTNUM` = `N` (mode number)

**\*GET**, `Par`,DDAM, `N`, `Item1`, `IT1NUM`

| Item1  | IT1NUM | Description                     |
|--------|--------|---------------------------------|
| DSHOCK |        | Shock design value of mode `N`. |

If multiple DDAM analyses are performed, the last calculated value will be returned.

**Postprocessing Items**

### \*GET Postprocessing Entity Items

- *\*GET Postprocessing Items, Entity = ACTIVE*
- *\*GET Postprocessing Items, Entity = ACUS*
- *\*GET Postprocessing Items, Entity = CAMP*
- *\*GET Postprocessing Items, Entity = CINT*
- *\*GET Postprocessing Items, Entity = CYCCALC*
- *\*GET Postprocessing Items, Entity = ELEM*
- *\*GET Postprocessing Items, Entity = ETAB*
- *\*GET Postprocessing Items, Entity = FSUM*
- *\*GET Postprocessing Items, Entity = GSRESULT*
- *\*GET Postprocessing Items, Entity = MEMBER*
- *\*GET Postprocessing Items, Entity = NODE*
- *\*GET Postprocessing Items, Entity = PATH*
- *\*GET Postprocessing Items, Entity = PLNSOL*
- *\*GET Postprocessing Items, Entity = PRENERGY*
- *\*GET Postprocessing Items, Entity = PRERR*
- *\*GET Postprocessing Items, Entity = RAD*
- *\*GET Postprocessing Items, Entity = RSTMAC*
- *\*GET Postprocessing Items, Entity = SECR*
- *\*GET Postprocessing Items, Entity = SECTION*
- *\*GET Postprocessing Items, Entity = SORT*
- *\*GET Postprocessing Items, Entity = SSUM*
- *\*GET Postprocessing Items, Entity = VARI*
- *\*GET Postprocessing Items, Entity = XFEM*

#### \*GET Postprocessing Items, Entity = ACTIVE

`Entity` = ACTIVE, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, ACTIVE, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| SET | LSTP | Current load step number. |
|  | SBST | Current substep number. |
|  | TIME | Time associated with current results in the database. |
|  | FREQ | Frequency (for ANTYPE=MODAL, HARMIC, SPECTR; load factor for ANTYPE=BUCKLE). |
|  | NSET | If Item2 is blank, number of data sets on result file. \* If Item2 = FIRST, IT2NUM = Loadstep, get set number of first substep of loadstep \* If Item2 = LAST, IT2NUM = Loadstep, get set number of last substep of loadstep |
| RSYS |  | Active results coordinate system. |

#### \*GET Postprocessing Items, Entity = ACUS

`Entity` = ACUS, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, ACUS, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| PWL |  | Radiated sound power level |
| PRES |  | Far-field pressure at a given point |
| PHASE |  | Far-field pressure phase at a given point |
| SPL |  | Far-field sound pressure level at a given point |
| SPLA |  | Far-field a-weighted sound pressure level at a given point |
| DG |  | Far-field directivity at a given point |
| PS |  | Far-field scattered pressure at a given point |
| TS |  | Far-field target strength at a given point |
| DFIN |  | Diffuse sound field incident power |
| SIMP |  | Magnitude of specific acoustic impedance on the selected surface |
| AIMP |  | Magnitude of acoustic impedance on the selected surface |
| MIMP |  | Magnitude of mechanical impedance on the selected surface |
| APRES |  | Magnitude of average pressure on the selected surface |
| FORC |  | Magnitude of average force on the selected surface |
| POWER |  | Acoustic power through the selected surface |
| BSPL |  | SPL over frequency band |
| BSPA |  | A-weighted SPL over frequency band |
| PWRF |  | Reference sound power |
| TL |  | Transmission loss |
| RL |  | Return loss |
| Item1 = PWL, PRES, SPL, SPLA, PHASE, DG, PS, and TS are available after issuing the [[prfar\|PRFAR]] or [[plfar\|PLFAR]] command. The maximum values are obtained from the current command. Item1 = SIMP, AIMP, MIMP, APRES, FORC, POWER, TL, and RL are available after issuing the corresponding [[pras\|PRAS]] command at the current frequency. The values are obtained at the current frequency, or at the last frequency for multiple load step and substep cases. Item1 = DFIN is available after the diffuse sound field solution. |  |  |

#### \*GET Postprocessing Items, Entity = CAMP

Available after [[plcamp|PLCAMP]] or [[prcamp|PRCAMP]] command is issued. `Entity` = CAMP, `ENTNUM` = `N` (mode number)

**\*GET**, `Par`, CAMP, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| NBMO |  | Number of modes in the Campbell diagram ( `ENTNUM` not required). This value is the maximum value for `N`. |
| NBST |  | Number of steps in the Campbell diagram: modal load steps with rotational velocity ( `ENTNUM` not required). This value is the maximum value for `M` (see Item1 = FREQ). |
| WHRL | `M` | Whirl of mode `N` at step `M` : -1 is backward whirl, 1 is forward whirl, and 0 is undetermined. For default `IT1NUM`, it corresponds to the whirl at the maximum rotational velocity. |
| VCRI |  | Critical speed for mode `N`. This value is available if an excitation is defined via the [[plcamp\|PLCAMP]] or [[prcamp\|PRCAMP]] command's `SLOPE` argument. (The unit of speed depends upon the `UNIT` value specified in those commands.) N does not correspond to the mode number if `FREQB` ( [[prcamp\|PRCAMP]] or [[plcamp\|PLCAMP]] command) is used. Instead, it represents the Nth mode number listed in the output of [[prcamp\|PRCAMP]] or [[plcamp\|PLCAMP]]. |
| FREQ | `M` | Natural frequency of mode (Hz) `N` at step `M`. It represents the complex part of the eigenvalue. |
| STAB | `M` | Stability value (Hz) of mode `N` at step `M`. It represents the real part of the eigenvalue. |
| UKEY | `M` | Instability key for mode `N` at step `M` : 0 is stable and 1 is unstable. For default `IT1NUM`, it corresponds to the stability over the whole rotational velocity range. |
| VSTA |  | Stability limit for mode N. This value is available when `SLOPE` is zero on the [[plcamp\|PLCAMP]] or [[prcamp\|PRCAMP]] command. (The unit of speed depends upon the `UNIT` value specified in those commands.) N does not correspond to the mode number if `FREQB` ( [[prcamp\|PRCAMP]] or [[plcamp\|PLCAMP]] command) is used. Instead, it represents the Nth mode number listed in the output of [[prcamp\|PRCAMP]] or [[plcamp\|PLCAMP]]. |

If the sorting is activated (Option= `ON` on the [[prcamp|PRCAMP]] and [[plcamp|PLCAMP]] commands), all the parameters retrieved are in the sorted order.

#### \*GET Postprocessing Items, Entity = CINT

`Entity` = CINT, `ENTNUM` = `CrackId` (required Crack ID number)

**\*GET**, `Par`, CINT, `CrackId`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| CTIP | ctnum | `IT1NUM` = Crack tip node number (required) `Item2` = CONTOUR `IT2NUM` = Contour number (default 1) Returns JINT value if crack ID is JINT type; otherwise, returns 0. `Item1` defaults to CTIP, `Item2` defaults to CONTOUR. |
| **Entity= CINT,** `ENTNUM` = CrackID (required Crack ID number) |  |  |
| **\*GET ,** `Par`, CINT, `CrackId`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`, `Item3`, `IT3NUM`, `Item4`, `IT4NUM` |  |  |
| **Item1** | **IT1NUM** | **Description** |
| CTIP | ctnum | `IT1NUM` = Crack tip node number (required) `Item2` = CONTOUR `IT2NUM` = Contour number (default 1) `Item3` = DTYPE `IT3NUM` = Data type (JINT, IIN1, IIN2, IIN3, K1, K2, K3, G1, G2, G3, GT, MFTX, MFTY, MFTZ, TSTRESS, CEXT, STTMAX, PSMAX, CSTAR, DLTA, DLTN, DLTK, R, UFAC, CRDX, CRDY, CRDZ, and APOS) FOR `IT3NUM` = STTMAX or PSMAX: \* Item4 = AINDEX (angle index) \* IT4NUM = Index value (1 to N+1; N = Maximum number of intervals for the sweep ( [[cint\|CINT]],RSWEEP). Returns specified data type value. FOR `IT3NUM` = DLTA, DLTN, DLTK, R, UFAC, CRDX, CRDY, CRDZ, APOS: \* Set `IT2NUM` = 1 Returns specified data type value. `Item1` defaults to CTIP, `Item2` defaults to CONTOUR, `Item3` defaults to DTYPE. DLTK in a 3D XFEM-based fatigue crack-growth analysis is evaluated based on the smoothed SIFS values. The actual DLTK value can be easily calculated by issuing **\*GET** for SIFS values and the stress (load) ratio. |
| **Entity= CINT,** `ENTNUM` = CrackID (required Crack ID number) |  |  |
| **\*GET ,** `Par`, CINT, `CrackId`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM` , |  |  |
| **Item1** | **IT1NUM** | **Description** |
| NNOD |  | Maximum number of nodes along the crack front. |
| **Entity= CINT,** `ENTNUM` = CrackID (required Crack ID number) |  |  |
| **\*GET ,** `Par`, CINT, `CrackId`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM` |  |  |
| **Item1** | **IT1NUM** | **Description** |
| NODE | ipos | IT1NUM = Position along the crack front (from 1 to NNOD). Default = 1. Returns node number at the given position along the crack front. (For XFEM, an internal node number is returned.) |

#### \*GET Postprocessing Items, Entity = CYCCALC

`Entity` = CYCCALC, `ENTNUM` = [[cycspec|CYCSPEC]] specification number Generate date for cyclic results using [[cyccalc|CYCCALC]] before retrieving those items.

**\*GET**, `Par`,CYCCALC, `spec`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Item2 | IT2NUM | Description |
|----|----|----|----|----|
| FREQ | frequency point | SECTOR | sector | [[cycspec\|CYCSPEC]] result at the IT1NUM frequency and IT2NUM sector |
|  |  | SECMAX | -  | [[cycspec\|CYCSPEC]] maximum result at the IT1NUM frequency |
|  |  | SECNUM | -  | [[cycspec\|CYCSPEC]] sector with the maximum result at the IT1NUM frequency |
|  |  | SECNODE | -  | [[cycspec\|CYCSPEC]] node in the sector with the maximum result at the IT1NUM frequency |
| The frequency point refers to the harmonic solution data set number (NSET on the [[set\|SET]] command) |  |  |  |  |

#### \*GET Postprocessing Items, Entity = ELEM

`Entity` = [[elem|ELEM]], `ENTNUM` = `N` (element number)

**\*GET**, `Par`, ELEM, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| SERR Some element- and material-type limitations apply. For more information, see the documentation for the [[prerr\|PRERR]] command. |  | Structural error energy. |
| SDSG |  | Absolute value of the maximum variation of any nodal stress component. |
| TERR |  | Thermal error energy. |
| TDSG |  | Absolute value of the maximum variation of any nodal thermal gradient component. |
| SENE |  | "Stiffness" energy or thermal heat dissipation. Same as TENE. |
| TENE |  | Thermal heat dissipation or "stiffness" energy. Same as SENE. |
| KENE |  | Kinetic energy. |
| ASENE |  | Amplitude “stiffness” energy. |
| PSENE |  | Peak “stiffness” energy. |
| AKENE |  | Amplitude kinetic energy. |
| PKENE |  | Peak kinetic energy. |
| DENE |  | Damping energy. |
| WEXT WEXT is calculated for element-based loading only (and not for nodal-force loading). WEXT is stored on elements to which loading has been applied; if surface elements are added on top of other elements, for example, and pressure loading is applied to the surface elements, WEXT is available for the surface elements only. |  | Work due to external load. |
| JHEAT |  | Element Joule heat generation (coupled-field calculation). |
| JS | X, Y, Z | Source current density (coupled-field calculation) in the global Cartesian coordinate system. |
| HS | X, Y, Z | Average element magnetic field intensity from current sources. |
| VOLU |  | Element volume, as calculated during solution. |
| ETAB | `Lab` | Value of element table item `Lab` for element `N` (see [[etable\|ETABLE]] command). |
| EFOR | `Nnum` | Element force at node `Nnum`. The force label is specified using Item2 = FX, FY, FZ, MX, MY, MZ, or HEAT. In a dynamics analysis, the element forces returned are based on the type of force requested. It is specified using the [[force\|FORCE]] command for all dynamics analyses, except for spectrum analyses where `ForceType` is used on the combination commands ( [[srss\|SRSS]], [[psdcom\|PSDCOM]], etc.). |
| SMISC | `Snum` | Value of element summable miscellaneous data at sequence number `Snum` (as used on [[etable\|ETABLE]] command). |
| NMISC | `Snum` | Value of element non-summable miscellaneous data at sequence number `Snum` (as used on [[etable\|ETABLE]] command). |
| FSOU |  | Element fluid flow source loading (poromechanics). |

#### \*GET Postprocessing Items, Entity = ETAB

`Entity` = ETAB, `ENTNUM = N` (column number)

**\*GET**, `Par`, ETAB, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| LAB |  | Label for column `N` of the element table ( [[etable\|ETABLE]] ). Returns a character parameter. |
| ELEM | `E` | Value in [[etable\|ETABLE]] column `N` for element number `E`. |

#### \*GET Postprocessing Items, Entity = FSUM

`Entity` = [[fsum|FSUM]], `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, FSUM, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ITEM | `Lab` | Value of item `Lab` from last [[fsum\|FSUM]] command. Valid labels are FX, FY, FZ, MX, MY, MZ, FLOW, HEAT, FLUX, etc. |

#### \*GET Postprocessing Items, Entity = GSRESULT

`Entity` = GSRESULT, `ENTNUM` = 0 (or blank) for generalized plane strain results in fiber direction

**\*GET**, `Par`, GSRESULT, 0, `Item1`, `IT1NUM`

| Item1  | IT1NUM | Description                                    |
|--------|--------|------------------------------------------------|
| LFIBER |        | Fiber length change at ending point.           |
| ROT    | X,Y    | Rotation angle of end plane about X or Y axis. |
| F      |        | Reaction force at ending point.                |
| M      | X,Y    | Reaction moment on ending plane.               |

#### \*GET Postprocessing Items, Entity = MEMBER

`Entity` = MEMBER, `ENTNUM` = `N` (GroupID)

**\*GET**, `Par`,MEMBER, `N`, `Item1`, `IT1NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| TEMP | MIN, MAX | Minimum or maximum temperature of members (individual reinforcings) with GroupID = `N` in the selected set of reinforcing elements. |

#### \*GET Postprocessing Items, Entity = NODE

`Entity` = `NODE`, `ENTNUM` = `N` (node number) for nodal degree-of-freedom results:

**\*GET**, `Par`, NODE, `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| U | X, Y, Z, SUM | X, Y, or Z structural displacement or vector sum. Alternative get functions: UX( `N` ), UY( `N` ), UZ( `N` ). |
| ROT | X, Y, Z, SUM | X, Y, or Z structural rotation or vector sum. Alternative get functions: ROTX( `N` ), ROTY( `N` ), ROTZ( `N` ). |
| TEMP |  | Temperature. For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use TBOT, TE2, TE3,..., TTOP instead of TEMP. Alternative get functions: TEMP( `N` ), TBOT( `N` ), TE2( `N` ), etc. |
| PRES |  | Pressure. Alternative get function: PRES( `N` ). |
| GFV1, GFV2, GFV3 |  | Nonlocal field values 1, 2, and 3. |
| VOLT |  | Electric potential. Alternative get function: VOLT( `N` ). |
| CONC |  | Concentration. |
| MAG |  | Magnetic scalar potential. Alternative get function: MAG( `N` ). |
| V | X, Y, Z, SUM | X, Y, or Z fluid velocity or vector sum in a fluid analysis. X, Y, or Z nodal velocity or vector sum in a structural transient analysis (analysis with [[antype\|ANTYPE]],TRANS). Alternative get functions: VX( `N` ), VY( `N` ), VZ( `N` ). |
| A | X, Y, Z, SUM | X, Y, or Z magnetic vector potential or vector sum in an electromagnetic analysis. X, Y, or Z nodal acceleration or vector sum in a structural transient analysis (analysis with [[antype\|ANTYPE]],TRANS). Alternative get functions: AX( `N` ), AY( `N` ), AZ( `N` ). |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| RF | FX, FY, FZ, MX, MY, MZ, CSGZ, BMOM, RATE, DVOL, FLOW, HEAT, AMPS or CHRG, FLUX, CURT, VLTG | Nodal reaction forces in the nodal coordinate system. The reaction forces returned are the total forces: static, plus damping, plus inertial, as appropriate based on analysis type (see [[prrsol\|PRRSOL]] command). The first exception is modal analyses and mode-superposition transient analyses where static forces are returned. The second exception is spectrum analyses where the [[prrfor\|PRRFOR]] logic is used internally. In this case, the reaction forces are based on the type of force requested (using `ForceType` with combination commands, such as [[srss\|SRSS]], [[psdcom\|PSDCOM]], etc.). |
| ORBT | A, B, PSI, PHI, YMAX, ZMAX, Whirl | Whirl orbit characteristics: \* A is the semi-major axis. \* B is the semi-minor axis. \* PSI is the angle between the local axis y and the major axis Y. \* PHI is the angle between initial position (t = 0) and major axis. \* YMAX is the maximum displacement along local y axis. \* ZMAX is the maximum displacement along local z axis. \* Whirl is the direction of an orbital motion (-1 is backward whirl, 1 is forward whirl, and 0 is undetermined). Angles PSI and PHI are in degrees and within the range of -180 through +180. Orbits are available only after issuing a [[prorb\|PRORB]] command. |
| Use this command carefully when N represents an internal node, as the nodal degrees of freedom may have different physical meanings. |  |  |

#### \*GET Postprocessing Items, Entity = PATH

Entity = PATH, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, PATH, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| MAX | `Lab` | Maximum value of path item `Lab` from last path operation. Valid labels are the user-defined labels on the [[pdef\|PDEF]] or [[pcalc\|PCALC]] command. |
| MAXPATH |  | Returns the maximum path number defined. |
| MIN | `Lab` | Minimum value of path item `Lab` from last path operation. Valid labels are the user-defined labels on the [[pdef\|PDEF]] or [[pcalc\|PCALC]] command. |
| LAST | `Lab` | Last value of path item `Lab` from last path operation. Valid labels are the user-defined labels on the [[pdef\|PDEF]] or [[pcalc\|PCALC]] command. |
| NODE |  | Value providing the number of nodes defining the path referenced in the last path operation. |
| ITEM | `Lab` | **Item2** = PATHPT, **IT2NUM** = n The value of `Lab` at the `n` th data point from the last path operation. |
| POINT | `n` | **Item2** = X,Y,Z, or CSYS. Returns information about the nth point on the current path. |
| NVAL |  | The number of path data points (the length of the data table) from the last path operation. |
| SET | `n` | **Item2** = NAME. Returns the name of the n th data set on the current path. |
| NUMPATH |  | Returns the number of paths defined. |

#### \*GET Postprocessing Items, Entity = PLNSOL

`Entity` = [[plnsol|PLNSOL]] You must issue the [[show|/SHOW]] command before commands that produce a graphical output when running in batch mode to produce/export graphic files. For more details, see [External Graphics Options](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS16_1.html#basexunijla61499) , `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, PLNSOL, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| MAX |  | Maximum value of item in last contour display ( [[plnsol\|PLNSOL]], [[plesol\|PLESOL]] ). |
| MIN |  | Minimum value of item in last contour display ( [[plnsol\|PLNSOL]], [[plesol\|PLESOL]] ). |
| BMAX |  | Maximum bound value of item in last contour display ( [[plnsol\|PLNSOL]], [[plesol\|PLESOL]] ). |
| BMIN |  | Minimum bound value of item in last contour display ( [[plnsol\|PLNSOL]], [[plesol\|PLESOL]] ). |

#### \*GET Postprocessing Items, Entity = PRENERGY

Available after the [[prenergy|PRENERGY]] command is issued. `Entity` = PRENERGY, `ENTNUM` = `N` (component number)

**\*GET**, `Par`, PRENERGY, `N`, `Item1`, `IT1NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| NCMP |  | Number of components ( `ENTNUM` not required). This value is the maximum value for `N`. |
| NENE |  | Number of energy types ( `ENTNUM` not required). This value is the maximum value for `M`. |
| TOTE | `M` | Total energy of type `M` of the model ( `ENTNUM` not required). Energy value is non-zero when `Cname1` is blank on prior [[prenergy\|PRENERGY]] command. |
| ENG | `M` | Energy of type `M` of component `N`. Energy value is non-zero when `Cname1` is specified on prior [[prenergy\|PRENERGY]] command. |
| PENG | `M` | Percentage of energy of type `M` of component `N`. Percentage of energy value is non-zero when `Cname1` is specified on prior [[prenergy\|PRENERGY]] command. |
| Ordering of `N` and `M` corresponds to [[prenergy\|PRENERGY]] output. |  |  |

#### \*GET Postprocessing Items, Entity = PRERR

`Entity` = PRERR, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, PRERR, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| SEPC\[  \] |  | Structural percent error in energy norm ( [[prerr\|PRERR]] ). |
| TEPC\[  \] |  | Thermal percent error in energy norm ( [[prerr\|PRERR]] ). |
| SERSM\[  \] |  | Structural error energy summation ( [[prerr\|PRERR]] ). |
| TERSM\[  \] |  | Thermal error energy summation ( [[prerr\|PRERR]] ). |
| SENSM\[  \] |  | Structural energy summation ( [[prerr\|PRERR]] ). |
| TENSM\[  \] |  | Thermal energy summation ( [[prerr\|PRERR]] ). |

Some element- and material-type limitations apply. For more information, see the documentation for the [[prerr|PRERR]] command.

#### \*GET Postprocessing Items, Entity = RAD

`Entity` = RAD, ENTNUM = 0 (or blank)

**\*GET**, `Par`, RAD, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| VFAVG |  | Value of the average view factor computed from the previous VFQUERY command. |

#### \*GET Postprocessing Items, Entity = RSTMAC

Available after [[rstmac|RSTMAC]] command is issued. `Entity` = [[rstmac|RSTMAC]], `ENTNUM` = `N` (solution number on `File1` )

**\*GET**, `Par`, RSTMAC, 0 or `N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| NS1 |  | Total number of solutions (modes for example) read on `File1`. See `Sbstep1` on the [[rstmac\|RSTMAC]] command. This value is the maximum value for `N`. |
| NS2 |  | Total number of solutions (modes for example) read on `File2`. See `Sbstep2` on the [[rstmac\|RSTMAC]] command. This value is the maximum value for `M` |
| MAC | M | Modal assurance criterion value (MAC) between the solution `N` read on `File1` and the solution `M` read on `File2`. `N` and `M` do not correspond to the substep (or mode) numbers if NS1 and NS2 are different from the total number of substeps (or modes). |
| MACCYC | M | Modal assurance criterion value (MAC) from compressed table for [[cyclic\|CYCLIC]] between the solution `N` read on `File1` and the solution `M` read on `File2`. `N` and `M` do not correspond to the substep (or mode) numbers if NS1 and NS2 are different from the total number of substeps (or modes). |

#### \*GET Postprocessing Items, Entity = SECR

`Entity` = SECR, `ENTNUM` = `n` (element number) For beam and pipe (including elbow) section results, return values for all elements if the element number ( `n` ) is blank or ALL.

**\*GET**, `Par`, SECR, n, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description | Item2 | IT2NUM |
|----|----|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component total stress | MAX - Returns maximum MIN - Returns minimum MAXY - Returns section Y location of maximum MAXZ - Returns section Z location of maximum MINY - Returns section Y location of minimum MINZ - Returns section Z location of minimum IVAL - Returns value at node or integration point at element I node JVAL - Returns value at node or integration point at element J node KVAL - Returns value at node or integration point at element K node ( `ELBOW290` ) - **For IVAL, JVAL, and KVAL:** The ALL (or blank) option for the element number is not valid. You must specify an element ( **n** ). | These values are applicable only when Item2 = IVAL, JVAL, or KVAL: When KEYOPT(15) = 0, this value is the section node number (which can be visualized via [[secplot\|SECPLOT]],,2). When KEYOPT(15) = 1 (or when using elbow elements), this value is the integration point number. |
|  | 1, 2, 3 | Principal stress value |  |  |
|  | INT | Stress intensity value |  |  |
|  | EQV | Equivalent stress value |  |  |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total strain |  |  |
|  | 1, 2, 3 | Principal total strain value |  |  |
|  | INT | Total strain intensity value |  |  |
|  | EQV | Equivalent total strain value |  |  |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain |  |  |
|  | 1, 2, 3 | Principal elastic strain value |  |  |
|  | INT | Elastic strain intensity value |  |  |
|  | EQV | Equivalent elastic strain value |  |  |
| EPTH | X, Y, Z, XY, YZ, XZ | Component thermal strain |  |  |
|  | 1, 2, 3 | Principal thermal strain value |  |  |
|  | INT | Thermal strain intensity value |  |  |
|  | EQV | Equivalent thermal strain value |  |  |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain |  |  |
|  | 1, 2, 3 | Principal plastic strain value |  |  |
|  | INT | Plastic strain intensity value |  |  |
|  | EQV | Equivalent plastic strain value |  |  |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain |  |  |
|  | 1, 2, 3 | Principal component creep strain value |  |  |
|  | INT | Component creep strain intensity value |  |  |
|  | EQV | Equivalent component creep strain value |  |  |
| EPTT | X, Y, Z, XY, YZ, XZ | Component total mechanical and thermal and swelling strain |  |  |
|  | 1, 2, 3 | Principal total mechanical and thermal and swelling strain value |  |  |
|  | INT | Total mechanical and thermal and swelling strain intensity value |  |  |
|  | EQV | Equivalent total mechanical and thermal and swelling strain value |  |  |
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain |  |  |
|  | 1, 2, 3 | Principal diffusion strain value |  |  |
|  | INT | Diffusion strain intensity value |  |  |
|  | EQV | Equivalent diffusion strain value |  |  |
| NL | SEPL | Plastic yield stress |  |  |
|  | SRAT | Plastic yielding (1 = actively yielding, 0 = not yielding) |  |  |
|  | HPRES | Hydrostatic pressure |  |  |
|  | EPEQ | Accumulated equivalent plastic strain |  |  |
|  | CREQ | Accumulated equivalent creep strain |  |  |
|  | PLWK | Plastic work/volume |  |  |
| YSIDX | TENS,SHEA | Yield surface activity status: 1 for yielded and 0 for not yielded. |  |  |
| FPIDX | TF01,SF01, TF02,SF02, TF03,SF03, TF04,SF04 | Failure plane surface activity status: 1 for yielded and 0 for not yielded. Tension and Shear failure status are available for all four sets of failure planes. |  |  |

#### \*GET Postprocessing Items, Entity = SECTION

`Entity` = SECTION, `ENTNUM` = `component` (listed below). Generate data for section stress results, using [[prsect|PRSECT]] before retrieving these items. Valid labels for `ENTNUM` are MEMBRANE, BENDING, SUM (Membrane+Bending), PEAK, and TOTAL. (The following items are not stored in the database and the values returned reflect the last quantities generated by [[prsect|PRSECT]] or [[plsect|PLSECT]].) Only MEMBRANE, BENDING, and SUM data are available after a [[plsect|PLSECT]] command. The MEMBRANE label is only valid with `Item1` = INSIDE.

**\*GET**, `Par`, SECTION, `component`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Item2 | Description |
|----|----|----|----|
| INSIDE | S | X, Y, Z, XY, YZ, XZ | Stress component at beginning of path. |
|  |  | 1, 2, 3 | Principal stress at beginning of path. |
|  |  | INT, EQV | Stress intensity or equivalent stress at beginning of path. |
| CENTER | S | X, Y, Z, XY, YZ, XZ | Stress component at midpoint of path. |
|  |  | 1, 2, 3 | Principal stress at midpoint of path. |
|  |  | INT, EQV | Stress intensity or equivalent stress at midpoint of path. |
| OUTSIDE | S | X, Y, Z, XY, YZ, XZ | Stress component at end of path. |
|  |  | 1, 2, 3 | Principal stress at end of path. |
|  |  | INT, EQV | Stress intensity or equivalent stress at end of path. |

#### \*GET Postprocessing Items, Entity = SORT

`Entity` = SORT, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, SORT, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| MAX |  | Maximum value of last sorted item ( [[nsort\|NSORT]] or [[esort\|ESORT]] command). |
| MIN |  | Minimum value of last sorted item ( [[nsort\|NSORT]] or [[esort\|ESORT]] command). |
| IMAX |  | Node/Element number where maximum value occurs. |
| IMIN |  | Node/Element number where minimum value occurs. |

#### \*GET Postprocessing Items, Entity = SSUM

`Entity` = SSUM, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, SSUM, 0, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1 | IT1NUM | Description |
|----|----|----|
| ITEM | `Lab` | Value of item `Lab` from last [[ssum\|SSUM]] command. Valid labels are the user-defined labels on the [[etable\|ETABLE]] command. |

#### \*GET Postprocessing Items, Entity = VARI

`Entity` = VARI, `ENTNUM` = `N` (variable number after POST26 data storage) (for complex values, only the real part is returned with Item1 = EXTREM)

**\*GET**, `Par,VARI,N`, `Item1`, `IT1NUM`, `Item2`, `IT2NUM`

| Item1  | IT1NUM | Description                                        |
|--------|--------|----------------------------------------------------|
| EXTREM | VMAX   | Maximum extreme value.                             |
|        | TMAX   | Time or frequency corresponding to VMAX.           |
|        | VMIN   | Minimum extreme value.                             |
|        | TMIN   | Time or frequency corresponding to VMIN.           |
|        | VLAST  | Last value.                                        |
|        | TLAST  | Time or frequency corresponding to VLAST.          |
|        | CVAR   | Covariance                                         |
| REAL   | f      | Real part of variable `N` at time or frequency f.  |
| IMAG   | f      | Imaginary part of variable `N` at frequency f.     |
| AMPL   | f      | Amplitude value of variable `N` at frequency f     |
| PHASE  | f      | Phase angle value of variable `N` at frequency f   |
| RSET   | `Snum` | Real part of variable `N` at location `Snum`.      |
| ISET   | `Snum` | Imaginary part of variable `N` at location `Snum`. |

#### \*GET Postprocessing Items, Entity = XFEM

`Entity` = XFEM, `ENTNUM` = 0 (or blank)

**\*GET**, `Par`, XFEM, 0, `Item1`, `IT1NUM`

| Item1 | IT1NUM           | Description                                       |
|-------|------------------|---------------------------------------------------|
| STAT  | `Element Number` | Status of the element: 0 = uncracked, 1 = cracked |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GET.html
