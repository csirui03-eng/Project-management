---
apdl: "*VPUT"
method: starvput
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.starvput
generated: 2026-08-22
tags: [mapdl-command]
---

# *VPUT

PyMAPDL: `mapdl.starvput(parr='', entity='', entnum='', item1='', it1num='', item2='', it2num='', kloop='', **kwargs)`

Restores array parameter values into the Mechanical APDL database.

## Parameters

**parr**: The name of the input vector array parameter. See [[starset|*SET]] for name restrictions. The parameter must exist as a dimensioned array ( [[dim|*DIM]] ) with data input.

**entity**: Entity keyword. Valid keywords are shown for `Entity` = in the table below.

**entnum**: The number of the entity (as shown for `ENTNUM` = in the table below).

**item1**: The name of a particular item for the given entity. Valid items are as shown in the `Item1` columns of the table below.

**it1num**: The number (or label) for the specified `Item1` (if any). Valid `IT1NUM` values are as shown in the `IT1NUM` columns of the table below. Some `Item1` labels do not require an `IT1NUM` value.

**item2**, **it2num**: A second set of item labels and numbers to further qualify the item for which data is to be stored. Most items do not require this level of information.

**kloop**

Field to be looped on:

- `0 or 2` - Loop on the `ENTNUM` field (default).
- `3` - Loop on the `Item1` field.
- `4` - Loop on the `IT1NUM` field. Successive items are as shown with `IT1NUM`.
- `5` - Loop on the `Item2` field.
- `6` - Loop on the `IT2NUM` field. Successive items are as shown with `IT2NUM`.

## Notes

### Argument descriptions

- `parr : str` - The name of the input vector array parameter. See [[starset|*SET]] for name restrictions. The parameter must exist as a dimensioned array ( [[dim|*DIM]] ) with data input.
- `entity : str` - Entity keyword. Valid keywords are shown for `Entity` = in the table below.
- `entnum : str` - The number of the entity (as shown for `ENTNUM` = in the table below).
- `item1 : str` - The name of a particular item for the given entity. Valid items are as shown in the `Item1` columns of the table below.
- `it1num : str` - The number (or label) for the specified `Item1` (if any). Valid `IT1NUM` values are as shown in the `IT1NUM` columns of the table below. Some `Item1` labels do not require an `IT1NUM` value.
- `item2, it2num : str` - A second set of item labels and numbers to further qualify the item for which data is to be stored. Most items do not require this level of information.
- `kloop : str` - Field to be looped on:
  - `0 or 2` - Loop on the `ENTNUM` field (default).
  - `3` - Loop on the `Item1` field.
  - `4` - Loop on the `IT1NUM` field. Successive items are as shown with `IT1NUM`.
  - `5` - Loop on the `Item2` field.
  - `6` - Loop on the `IT2NUM` field. Successive items are as shown with `IT2NUM`.

The **\*VPUT** command is not supported for PowerGraphics displays. Inconsistent results may be obtained if this command is not used in [[graphics|/GRAPHICS]], FULL.

Plot and print operations entered via the GUI ( Utility Menu\> Pltcrtls, Utility Menu\> Plot ) incorporate the [[avprin|AVPRIN]] command. This means that the principal and equivalent values are recalculated. If you use **\*VPUT** to put data back into the database, issue the plot commands from the command line to preserve your data.

This operation is basically the inverse of the [[starvget|*VGET]] operation. Vector items are put directly (without any coordinate system transformation) into the Mechanical APDL database. Items can only replace existing items of the database and not create new items. Degree of freedom results that are replaced in the database are available for all subsequent postprocessing operations. Other results are changed temporarily and are available mainly for the immediately following print and display operations. The vector specification [[vcum|*VCUM]] does not apply to this command. The valid labels for the location fields ( `Entity`, `ENTNUM`, `Item1`, and `IT1NUM` ) are listed below. `Item2` and `IT2NUM` are not currently used. Not all items from the [[starvget|*VGET]] list are allowed on **\*VPUT**, as putting values into some locations could cause the database to be inconsistent.

This command is valid in any processor.

#### \*VPUT - POST1 Items

`Entity` = NODE, `ENTNUM` = `n` (node number)

| Item1 | IT1NUM | Description |
|----|----|----|
| Valid labels for nodal degree of freedom results are: |  |  |
| U | X, Y, Z | X, Y, or Z structural displacement. |
| ROT | X, Y, Z | X, Y, or Z structural rotation. |
| TEMP |  | Temperature. For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use TBOT, TE2, TE3,..., TTOP instead of TEMP. Alternative get functions: TEMP(N), TBOT(N), TE2(N), etc. |
| PRES |  | Pressure. |
| VOLT |  | Electric potential. |
| MAG |  | Magnetic scalar potential. |
| V | X, Y, Z | X, Y, or Z fluid velocity. X, Y, or Z nodal velocity in a transient structural analysis (analysis with [[antype\|ANTYPE]],TRANS). |
| A | X, Y, Z | X, Y, or Z magnetic vector potential. X, Y, or Z nodal acceleration in a transient structural analysis (analysis with [[antype\|ANTYPE]],TRANS). |
| CONC |  | Concentration. |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| Valid labels for element nodal results are: |  |  |
| Item1 | IT1NUM | Description |
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
| TG | X, Y, Z | Component thermal gradient. |
| TF | X, Y, Z | Component thermal flux. |
| PG | X, Y, Z | Component pressure gradient. |
| EF | X, Y, Z | Component electric field. |
| D | X, Y, Z | Component electric flux density. |
| H | X, Y, Z | Component magnetic field intensity. |
| B | X, Y, Z | Component magnetic flux density. |
| FMAG | X, Y, Z | Component electromagnetic force. |
| **Entity= ELEM,** `ENTNUM` = `n` (element number) |  |  |
| Valid labels for element results are: |  |  |
| Item1 | IT1NUM | Description |
| ETAB | Lab | Any user-defined element table label ( [[etable\|ETABLE]] ). |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VPUT_st.html
