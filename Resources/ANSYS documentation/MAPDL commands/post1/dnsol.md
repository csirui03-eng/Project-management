---
apdl: "DNSOL"
method: dnsol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.dnsol
generated: 2026-08-22
tags: [mapdl-command]
---

# DNSOL

PyMAPDL: `mapdl.dnsol(node='', item='', comp='', v1='', v2='', v3='', v4='', v5='', v6='', datakey='', **kwargs)`

Defines or modifies solution results at a node.

## Parameters

**node**: Node for which results are specified. If ALL, apply to all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

**item**: Label identifying results, see *DNSOL - Valid Item and Component Labels*. Some items also require a component label.

**comp**: Component of the item. Valid component labels are shown *DNSOL - Valid Item and Component Labels* below.

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**: Value assigned to result. If zero, a zero value will be assigned. If blank, the value remains unchanged. Additional values (if any) assigned to the remaining components (in the order corresponding to the `Comp` list shown below for the specified `Item` (starting from the specified `Comp` label and proceeding to the right).

**datakey**

Key to specify which data is modified:

- `AUTO` - [Nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are used if available. Otherwise, the element-based data is used if available. (Default)
- `ESOL` - Only element-based results are used. If they are not available, the command is ignored.
- `NAR` - Only nodal-averaged results are used. If they are not available, the command is ignored.

## Notes

**DNSOL** can be used only with FULL graphics activated ( [[graphics|/GRAPHICS]],FULL); it will not work correctly with PowerGraphics activated.

**DNSOL** defines or modifies solution results in the database at a node. For example, **DNSOL**,35,U,X,.001,.002,.001 assigns values 0.001, 0.002, and 0.001 to UX, UY, and UZ (respectively) for node 35. All results that are changed in the database, including the nodal degree of freedom results, are available for all subsequent operations. All data is stored in the solution coordinate system but is displayed in the results coordinate system ( [[rsys|RSYS]] ). Use [[prnsol|PRNSOL]] to list the current results.

Data input by **DNSOL** is stored in temporary space and does not replace information in the database. Therefore, data input by this command may be overwritten if a change is made to the selected set of nodes or if an output operation acts on a new `Item`.

Issuing **DNSOL** requires you to place the data type (stress/strain) in the element nodal records. To work around this requirement, use the [[desol|DESOL]] command or equivalent path to add a dummy element stress/strain record.

Result items are available depending on element type; check the individual element for availability. Valid item and component labels for element results are shown in *DNSOL - Valid Item and Component Labels*.

### Using **DNSOL** with Nodal-Averaged Results

If [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) ( [[outres|OUTRES]],NAR or another nodal-averaged label) are in the database, then **DNSOL** acts on the nodal-averaged data for the applicable items (S, EPEL, EPPL, EPCR, EPTH, EPSW) by default. You can change this behavior via the `DataKey` argument.

**DNSOL** behavior differs when the command acts on [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost). The nodal-averaged results that are defined or modified will be apparent in subsequent command operations (for example [[prnsol|PRNSOL]], [[plnsol|PLNSOL]] ) in both full model graphics mode ( [[graphics|/GRAPHICS]],FULL) and PowerGraphics mode ( [[graphics|/GRAPHICS]],POWER). The resultant data is stored in the global Cartesian coordinate system but is displayed in the results coordinate system ( [[rsys|RSYS]] ). **DNSOL** can only be applied to nodal-averaged results if they are already in the database; otherwise, the modifications are applied to the element-based solution in temporary memory. The modified nodal-averaged results are not saved to the results file automatically. To save separate records of modified nodal-averaged results, use [[lcwrite|LCWRITE]], [[rappnd|RAPPND]], or [[reswrite|RESWRITE]].

**DNSOL** can only modify component values ( `Comp` = X, Y, Z, XY, YZ, or XZ) for nodal- averaged results. If you attempt to modify principal values using **DNSOL** with `DataKey` = AUTO, then the modification is applied to element-based results if they are available.

#### DNSOL - Valid Item and Component Labels

Valid Item and Component Labels for Nodal DOF Results

| Item       | Comp    | Description                           |
|------------|---------|---------------------------------------|
| U          | X, Y, Z | X, Y, or Z structural displacement.   |
| ROT        | X, Y, Z | X, Y, or Z structural rotation.       |
| TEMP\[ \]  |         | Temperature.                          |
| PRES       |         | Pressure.                             |
| VOLT       |         | Electric potential.                   |
| MAG        |         | Magnetic scalar potential.            |
| V          | X, Y, Z | X, Y, or Z fluid velocity.            |
| A          | X, Y, Z | X, Y, or Z magnetic vector potential. |
| CONC       |         | Concentration.                        |

(table not available in the PyMAPDL source, see the Ansys help page)

For `SHELL131` and `SHELL132` elements with KEYOPT(3) = 0 or 1, use the labels TBOT, TE2, TE3,..., TTOP instead of TEMP.

For these component values, [nodal-averaged results](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_2.html#nodeavepost) are modified if they are available in the results file and `DataKey` = AUTO or NAR.

Modifying principal values of nodal-averaged results is not supported.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DNSOL.html
