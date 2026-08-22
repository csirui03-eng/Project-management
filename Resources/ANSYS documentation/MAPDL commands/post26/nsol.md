---
apdl: "NSOL"
method: nsol
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.nsol
generated: 2026-08-22
tags: [mapdl-command]
---

# NSOL

PyMAPDL: `mapdl.nsol(nvar='', node='', item='', comp='', name='', sector='', **kwargs)`

Specifies nodal data to be stored from the results file.

## Parameters

**nvar**: Arbitrary reference number assigned to this variable. Variable numbers can be 2 to `NV` ( [[numvar|NUMVAR]] ). Overwrites any existing results for this variable.

**node**: Node for which data are to be stored.

**item**: Label identifying the item. Valid item labels are shown in the table below. Some items also require a component label.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**name**: Thirty-two character name identifying the item on printouts and displays. Defaults to a label formed by concatenating the first four characters of the `Item` and `Comp` labels.

**sector**: For a full harmonic cyclic symmetry solution, the sector number for which the results from NODE are to be stored.

## Notes

Stores nodal degree of freedom and solution results in a variable. For more information, see Data Interpreted in the Nodal Coordinate System in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html).

For `SECTOR` \>1, the result is in the nodal coordinate system of the base sector, and it is rotated to the expanded sector's location. Refer to [Using the /CYCEXPAND Command](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cycsym/advcycpost.html#)

### NSOL - Valid Item and Component Labels

Valid Item and Component Labels **NSOL**, `NVAR,NODE,Item,Comp,Name`

Valid item and component labels for nodal degree of freedom results are:

| Item | Comp | Description |
|----|----|----|
| U | X, Y, Z | X, Y, or Z structural displacement. |
| ROT | X, Y, Z | X, Y, or Z structural rotation. |
| TEMP\[  \] |  | Temperature. |
| PRES |  | Pressure. |
| GFV1, GFV2, GFV3 |  | Nonlocal field values 1, 2, and 3. |
| VOLT |  | Electric potential. |
| MAG |  | Magnetic scalar potential. |
| V | X, Y, Z | X, Y, or Z fluid velocity in a fluid analysis. |
| A | X, Y, Z | X, Y, or Z magnetic vector potential in an electromagnetic analysis. |
| CONC |  | Concentration. |
| VEL | X, Y, Z | X, Y, or Z velocity in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| ACC | X, Y, Z | X, Y, or Z acceleration in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| OMG | X, Y, Z | X, Y, or Z rotational velocity in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| DMG | X, Y, Z | X, Y, or Z rotational acceleration in a structural transient dynamic analysis ( [[antype\|ANTYPE]],TRANS). |
| CURR |  | Current. |
| EMF |  | Electromotive force drop. |
| SPL |  | Sound pressure level. |
| SPLA |  | A-weighted sound pressure level (dBA). |
| ENKE |  | Acoustic energy density |

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3,. .., TTOP instead of TEMP.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSOL.html
