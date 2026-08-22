---
apdl: "NSEL"
method: nsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.nsel
generated: 2026-08-22
tags: [mapdl-command]
---

# NSEL

PyMAPDL: `mapdl.nsel(type_='', item='', comp='', vmin='', vmax='', vinc='', kabs='', **kwargs)`

Selects a subset of nodes.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Restore the full set.
- `NONE` - Unselect the full set.
- `INVE` - Invert the current set (selected becomes unselected and vice versa).
- `STAT` - Display the current select status.

**item**: Label identifying data. Valid item labels are shown in the table below. Some items also require a component label. If `Item` = PICK (or simply "P"), graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). Defaults to NODE.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**vmin**: Minimum value of item range. Ranges are node numbers, set numbers, coordinate values, load values, or result values as appropriate for the item. A component name (as specified on the [[cm|CM]] command) may also be substituted for `VMIN` ( `VMAX` and `VINC` are ignored).

**vmax**: Maximum value of item range. `VMAX` defaults to `VMIN` for input values. For result values, `VMAX` defaults to infinity if `VMIN` is positive, or to zero if `VMIN` is negative.

**vinc**: Value increment within range. Used only with integer ranges (such as for node and set numbers). Defaults to 1. `VINC` cannot be negative.

**kabs**

Absolute value key:

- `0` - Check sign of value during selection.
- `1` - Use absolute value during selection (sign ignored).

## Notes

Selects a subset of nodes. For example, to select a new set of nodes based on node numbers 1 through 7, use **NSEL**,S,NODE,,1,7. The subset is used when the ALL label is entered (or implied) on other commands, such as [[nlist|NLIST]],ALL. Only data identified by node number are selected. Data are flagged as selected and unselected; no data are actually deleted from the database.

When selecting nodes by results, the full graphics value is used, regardless of whether PowerGraphics is on.

Solution result data consists of two types, 1) nodal degree of freedom-results initially calculated at the nodes (such as displacement, temperature, pressure, etc.), and 2) element-results initially calculated elsewhere (such as at an element integration point or thickness location) and then recalculated at the nodes (such as stresses, strains, etc.). Various element results also depend upon the recalculation method and the selected results location ( [[avprin|AVPRIN]], [[rsys|RSYS]], [[force|FORCE]], [[layer|LAYER]] and [[shell|SHELL]] ).

You must have all the nodes (corner and midside nodes) on the external face of the element selected to use `Item` = EXT.

This command is valid in any processor.

For Selects based on non-integer numbers (coordinates, results, etc.), items that are within the range VMIN- `Toler` and VMAX+ `Toler` are selected. The default tolerance `Toler` is based on the relative values of VMIN and VMAX as follows:

- If VMIN = VMAX, `Toler` = 0.005 x VMIN.
- If VMIN = VMAX = 0.0, `Toler` = 1.0E-6.
- If VMAX ≠ VMIN, `Toler` = 1.0E-8 x (VMAX-VMIN).

Use the [SELTOL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SELTOL.html#SELTOL.menupath) [[seltol|SELTOL]] command to override this default and specify `Toler` explicitly.

### NSEL - Valid Item and Component Labels

Valid Item and Component Labels **NSEL**, `Type,Item,Comp,VMIN,VMAX,VINC,KABS`

Valid item and component labels for input values are:

| Item | Comp | Description |
|----|----|----|
| NODE |  | Node number. |
| EXT |  | Nodes on exterior of selected elements (ignore remaining fields). |
| LOC | X, Y, Z | X, Y, or Z location in the active coordinate system. |
| ANG | XY, YZ, ZX | THXY, THYZ, or THZX rotation angle. |
| M |  | Master node number. |
| CP |  | Coupled set number. |
| CE |  | Constraint equation set number. |
| D | U | Any of X, Y, or Z structural displacements. Amplitude only, if complex. |
| " | UX, UY, UZ | X, Y, or Z structural displacement. Amplitude only, if complex. |
| " | ROT | Any of X, Y, or Z structural rotations. Amplitude only, if complex. |
| " | ROTX, ROTY, ROTZ | X, Y, or Z structural rotation. Amplitude only, if complex. |
| " | TEMP, TBOT, TE2, TE3,..., TTOP | Temperature. |
| " | PRES | Pressure (for example, PRES degree of freedom for acoustic elements). |
| " | VOLT | Electric potential. |
| " | MAG | Magnetic scalar potential. |
| " | V | Any of X, Y, or Z fluid velocities. |
| " | VX, VY, VZ | X, Y, or Z fluid velocity. |
| " | AZ | 2D magnetic vector potential. Amplitude only, if complex. |
| " | CURR | Current. |
| " | EMF | Electromotive force drop. |
| F | F | Any of X, Y, or Z structural forces. Amplitude only, if complex. |
| " | FX, FY, FZ | X, Y, or Z structural force. Amplitude only, if complex. |
| " | M | Any of X, Y, or Z structural moments. Amplitude only, if complex |
| " | MX, MY, MZ | X, Y, or Z structural moment. Amplitude only, if complex. |
| " | HEAT, HBOT, HE2, HE3,..., HTOP | Heat flow. |
| " | FLOW | Fluid flow. |
| " | AMPS | Current flow. |
| " | FLUX | Magnetic flux. |
| " | CSGZ | Magnetic current segment component. Amplitude only, if complex. |
| " | CHRG | Electric charge. |
| " | CHRGD | Electric charge density. |
| BF | TEMP | Nodal temperature. |
| " | FLUE | Nodal fluence. |
| " | HGEN | Nodal heat generation rate. |
| " | JS | Any of X, Y, or Z current densities. Amplitude only, if complex. |
| " | JSX, JSY, JSZ | X, Y, or Z current density. Amplitude only, if complex. |
| " | MVDI | Magnetic virtual displacements flag. |
| " | DGEN | Nodal diffusing substance generation rate. |

### NSEL - Valid Item and Component Labels for Nodal DOF Result Values

| Item | Comp         | Description                                         |
|------|--------------|-----------------------------------------------------|
| U    | X, Y, Z, SUM | X, Y, or Z structural displacement or vector sum.   |
| ROT  | X, Y, Z, SUM | X, Y, or Z structural rotation or vector sum.       |
| TEMP |              | Temperature.                                        |
| PRES |              | Pressure.                                           |
| VOLT |              | Electric potential.                                 |
| MAG  |              | Magnetic scalar potential.                          |
| V    | X, Y, Z, SUM | X, Y, or Z fluid velocity or vector sum.            |
| A    | X, Y, Z, SUM | X, Y, or Z magnetic vector potential or vector sum. |
| CONC |              | Concentration.                                      |
| CURR |              | Current.                                            |
| EMF  |              | Electromotive force drop.                           |

### NSEL - Valid Item and Component Labels for Element Result Values

| Item | Comp | Description |
|----|----|----|
| S | X, Y, Z, XY, YZ, XZ | Component stress. |
| " | 1, 2, 3 | Principal stress. |
| " | INT, EQV | Stress intensity or equivalent stress. |
| EPTO | X, Y, Z, XY, YZ, XZ | Component total strain (EPEL + EPPL + EPCR). |
| " | 1,2,3 | Principal total strain. |
| " | INT, EQV | Total strain intensity or total equivalent strain. |
| EPEL | X, Y, Z, XY, YZ, XZ | Component elastic strain. |
| " | 1, 2, 3 | Principal elastic strain. |
| " | INT, EQV | Elastic strain intensity or elastic equivalent strain. |
| EPPL | X, Y, Z, XY, YZ, XZ | Component plastic strain. |
| " | 1,2,3 | Principal plastic strain. |
| " | INT, EQV | Plastic strain intensity or plastic equivalent strain. |
| EPCR | X, Y, Z, XY, YZ, XZ | Component creep strain. |
| " | 1,2,3 | Principal creep strain. |
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

For more information on the meaning of contact status and its possible values, see [Reviewing Results in POST1](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_revresu.html#ctecpostslide)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSEL.html
