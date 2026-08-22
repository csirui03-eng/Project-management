---
apdl: "VSEL"
method: vsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.vsel
generated: 2026-08-22
tags: [mapdl-command]
---

# VSEL

PyMAPDL: `mapdl.vsel(type_='', item='', comp='', vmin='', vmax='', vinc='', kswp='', **kwargs)`

Selects a subset of volumes.

## Parameters

**type_**

Label identifying the type of volume select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Restore the full set.
- `NONE` - Unselect the full set.
- `INVE` - Invert the current set (selected becomes unselected and vice versa).
- `STAT` - Display the current select status.

**item**: Label identifying data. Valid item labels are shown in the table below. Some items also require a component label. If `Item` = PICK (or simply "P"), graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). Defaults to VOLU.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**vmin**: Minimum value of item range. Ranges are volume numbers, coordinate values, attribute numbers, etc., as appropriate for the item. A component name (as specified on the [[cm|CM]] command) may also be substituted for `VMIN` ( `VMAX` and `VINC` are ignored). If `Item` = MAT, TYPE, REAL, or ESYS and if `VMIN` is positive, the absolute value of `Item` is compared against the range for selection; if `VMIN` is negative, the signed value of `Item` is compared. See the [[vlist|VLIST]] command for a discussion of signed attributes.

**vmax**: Maximum value of item range. `VMAX` defaults to `VMIN`.

**vinc**: Value increment within range. Used only with integer ranges (such as for volume numbers). Defaults to 1. `VINC` cannot be negative.

**kswp**

Specifies whether only volumes are to be selected:

- `0` - Select volumes only.
- `1` - Select volumes, as well as keypoints, lines, areas, nodes, and elements associated with selected volumes. Valid only with `Type` = S.

## Notes

Selects volumes based on values of a labeled item and component. For example, to select a new set of volumes based on volume numbers 1 through 7, use **VSEL**,S,VOLU,,1,7. The subset is used when the ALL label is entered (or implied) on other commands, such as [[vlist|VLIST]],ALL. Only data identified by volume number are selected. Data are flagged as selected and unselected; no data are actually deleted from the database.

This command is valid in any processor.

For Selects based on non-integer numbers (coordinates, results, etc.), items that are within the range VMIN- `Toler` and VMAX+ `Toler` are selected. The default tolerance `Toler` is based on the relative values of VMIN and VMAX as follows:

- If VMIN = VMAX, `Toler` = 0.005 x VMIN.
- If VMIN = VMAX = 0.0, `Toler` = 1.0E-6.
- If VMAX ≠ VMIN, `Toler` = 1.0E-8 x (VMAX-VMIN).

Use the [SELTOL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SELTOL.html#SELTOL.menupath) [[seltol|SELTOL]] command to override this default and specify `Toler` explicitly.

### VSEL - Valid Item and Component Labels

**VSEL** `Type, Item, Comp, VMIN, VMAX, VINC, KABS`

| Item | Comp | Description |
|----|----|----|
| VOLU |  | Volume number. |
| LOC | X, Y, Z | X, Y, or Z center (picking "hot spot" location in the active coordinate system). |
| MAT |  | Material number associated with the volume. |
| TYPE |  | Element type number associated with the volume. |
| REAL |  | Real constant set number associated with the volume. |
| ESYS |  | Element coordinate system associated with the volume. |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSEL.html
