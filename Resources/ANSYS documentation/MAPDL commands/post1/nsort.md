---
apdl: "NSORT"
method: nsort
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.nsort
generated: 2026-08-22
tags: [mapdl-command]
---

# NSORT

PyMAPDL: `mapdl.nsort(item='', comp='', order='', kabs='', numb='', sel='', **kwargs)`

Sorts nodal data.

## Parameters

**item**: Label identifying the item to be sorted on. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**order**

Order of sort operation:

- `0` - Sort into descending order.
- `1` - Sort into ascending order.

**kabs**

Absolute value key:

- `0` - Sort according to real value.
- `1` - Sort according to absolute value.

**numb**: Number of nodal data records to be sorted in ascending or descending order ( `ORDER` ) before sort is stopped (remainder will be in unsorted sequence) (defaults to all nodes).

**sel**

Allows selection of nodes in the sorted field.

- `(blank)` - No selection (default).
- `SELECT` - Select the nodes in the sorted list.

## Notes

Values are in the active coordinate system ( [[csys|CSYS]] for input data or [[rsys|RSYS]] for results data). Various element results also depend upon the recalculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], [[shell|SHELL]], [[esel|ESEL]], and [[nsel|NSEL]] ). If simultaneous load cases are stored, the last sorted sequence formed from any load case applies to all load cases. Use [[nusort|NUSORT]] to restore the original order. This command is not valid with PowerGraphics.

### NSORT - Valid Item and Component Labels

Valid Item and Component Labels **NSORT**, `Item,Comp,ORDER,KABS,NUMB,SEL`

Valid item and component labels for input values are:

| Item | Comp       | Description                         |
|------|------------|-------------------------------------|
| LOC  | X, Y, Z    | X, Y, or Z location.                |
| ANG  | XY, YZ, ZX | THXY, THYZ, or THZX rotation angle. |

### NSORT - Valid Item and Component Labels for Nodal DOF Result Values

| Item | Comp | Description |
|----|----|----|
| U | X, Y, Z, SUM | X, Y, or Z structural displacement or vector sum. |
| ROT | X, Y, Z, SUM | X, Y, or Z structural rotation or vector sum. |
| TEMP |  | Temperature (includes TEMP, TBOT, TE2, TE3,..., TTOP values). |
| PRES |  | Pressure. |
| VOLT |  | Electric potential. |
| MAG |  | Magnetic scalar potential. |
| V | X, Y, Z, SUM | X, Y, or Z fluid velocity or vector sum. |
| A | X, Y, Z, SUM | X, Y, or Z magnetic vector potential or vector sum. |
| CONC |  | Concentration |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |

### NSORT - Valid Item and Component Labels for Element Result Values

| Item | Comp | Description |
|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component stress. |
| " | 1, 2,3 | Principal stress. |
| " | INT, EQV | Stress intensity or equivalent stress. |
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
| EPDI | X, Y, Z, XY, YZ, XZ | Component diffusion strain. |
| " | 1, 2, 3 | Principal diffusion strain. |
| " | INT, EQV | Diffusion strain intensity or diffusion equivalent strain. |
| NL | SEPL | Equivalent stress (from stress-strain curve). |
| " | SRAT | Stress state ratio. |
| " | HPRES | Hydrostatic pressure. |
| " | EPEQ | Accumulated equivalent plastic strain. |
| " | PSV | Plastic state variable. |
| " | PLWK | Plastic work/volume. |
| FAIL | MAX | Maximum of all active failure criteria defined at the current location. (See the [[fctyp\|FCTYP]] command for details.) |
| " | EMAX | Maximum Strain Failure Criterion |
| " | SMAX | Maximum Stress Failure Criterion |
| " | TWSI | Tsai-Wu Strength Index Failure Criterion |
| " | TWSR | Inverse of Tsai-Wu Strength Ratio Index Failure Criterion |
| " | HFIB | Hashin Fiber Failure Criterion. \[  \]\[  \] |
| " | HMAT | Hashin Matrix Failure Criterion. \[  \]\[  \] |
| " | PFIB | Puck Fiber Failure Criterion. \[  \]\[  \] |
| " | PMAT | Puck Matrix Failure Criterion. \[  \]\[  \] |
| " | USR1, USR2,..., USR9 | User-defined failure criteria \[  \]\[  \]\[  \] |
| CONT | STAT | Contact status. |
| " | PENE | Contact penetration. |
| " | PRES | Contact pressure. |
| " | SFRIC | Contact friction stress. |
| " | STOT | Contact total stress (pressure plus friction). |
| " | SLIDE | Contact sliding distance. |
| TG | X, Y, Z, SUM | Component thermal gradient or vector sum. |
| TF | X, Y, Z, SUM | Component thermal flux or vector sum. |
| PG | X, Y, Z, SUM | Component pressure gradient or vector sum. |
| EF | X, Y, Z, SUM | Component electric field or vector sum. |
| D | X, Y, Z, SUM | Component electric flux density or vector sum. |
| H | X, Y, Z, SUM | Component magnetic field intensity or vector sum. |
| B | X, Y, Z, SUM | Component magnetic flux density or vector sum. |
| CG | X, Y, Z, SUM | Component concentration gradient or vector sum |
| DF | X, Y, Z, SUM | Component diffusion flux density or vector sum |
| FMAG | X, Y, Z, SUM | Component electromagnetic forces or vector sum. |

Works only if failure criteria information is provided. (For more information, see the documentation for the [[fc|FC]] and [[tb|TB]] commands.)

Must be added via the [[fctyp|FCTYP]] command first.

Works only if user failure criteria routine is provided.

For more information about contact status and its possible values, see [Reviewing Results in POST1](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_revresu.html#ctecpostslide)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSORT.html
