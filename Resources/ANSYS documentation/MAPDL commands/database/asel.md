---
apdl: "ASEL"
method: asel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.asel
generated: 2026-08-22
tags: [mapdl-command]
---

# ASEL

PyMAPDL: `mapdl.asel(type_='', item='', comp='', vmin='', vmax='', vinc='', kswp='', **kwargs)`

Selects a subset of areas.

> [!NOTE]
> Starting with PyMAPDL v0.66.0, you can use "P" as a second argument to select entities interactively. A window pops up allowing you to select, unselect, add or reselect entities depending on the first argument `type_`. An array with the ids of new selection is returned when the window is closed.

**Command default:**

All areas are selected.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set (default)
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Restore the full set.
- `NONE` - Unselect the full set.
- `INVE` - Invert the current set (selected becomes unselected and vice versa).
- `STAT` - Display the current select status.

**item**: Label identifying data. Valid item labels are shown in *ASEL - Valid Item and Component Labels*. Some items also require a component label. If `Item` = PICK (or simply "P"), graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). Defaults to AREA.

**comp**: Component of the item (if required). Valid component labels are shown in *ASEL - Valid Item and Component Labels*.

**vmin**: Minimum value of item range. Ranges are area numbers, coordinate values, attribute numbers, etc., as appropriate for the item. A component name (as specified on the [[cm|CM]] command) may also be substituted for `VMIN` ( `VMAX` and `VINC` are ignored). If `Item` = MAT, TYPE, REAL, or ESYS and if `VMIN` is positive, the absolute value of `Item` is compared against the range for selection; if `VMIN` is negative, the signed value of `Item` is compared. See the [[alist|ALIST]] command for a discussion of signed attributes.

**vmax**: Maximum value of item range. `VMAX` defaults to `VMIN`.

**vinc**: Value increment within range. Used only with integer ranges (such as for area numbers). Defaults to 1. `VINC` cannot be negative.

**kswp**

Specifies whether only areas are to be selected:

- `0` - Select areas only.
- `1` - Select areas, as well as keypoints, lines, nodes, and elements associated with selected areas. Valid only with `Type` = S.

## Notes

Selects a subset of areas. For example, to select those areas with area numbers 1 through 7, use **ASEL**,S,AREA,,1,7. The selected subset is then used when the ALL label is entered (or implied) on other commands, such as [[alist|ALIST]],ALL. Only data identified by area number are selected. Data are flagged as selected and unselected; no data are actually deleted from the database.

In a cyclic symmetry analysis, area hot spots can be modified. Consequently, the result of an area selection may be different before and after the [[cyclic|CYCLIC]] command.

If `Item` = ACCA, the command selects only those areas that were created by concatenation. The `KSWP` field is processed, but the `Comp`, `VMIN`, `VMAX`, and `VINC` fields are ignored.

This command is valid in any processor.

For Selects based on non-integer numbers (coordinates, results, etc.), items that are within the range VMIN- `Toler` and VMAX+ `Toler` are selected. The default tolerance `Toler` is based on the relative values of VMIN and VMAX as follows:

- If VMIN = VMAX, `Toler` = 0.005 x VMIN.
- If VMIN = VMAX = 0.0, `Toler` = 1.0E-6.
- If VMAX ≠ VMIN, `Toler` = 1.0E-8 x (VMAX-VMIN).

Use the [SELTOL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SELTOL.html#SELTOL.menupath) [[seltol|SELTOL]] command to override this default and specify `Toler` explicitly.

### ASEL - Valid Item and Component Labels

Valid Item and Component Labels **ASEL**, `Type Item,Comp,VMIN,VMAX,VINC,KSWP`

| Item | Comp | Description |
|----|----|----|
| AREA |  | Area number. |
| EXT |  | Area numbers on exterior of selected volumes (ignore remaining fields). |
| LOC | X, Y, Z | X, Y, or Z center (picking "hot spot" location in the active coordinate system). |
| HPT |  | Area number (selects only areas with associated hard points). |
| MAT |  | Material number associated with the area. |
| TYPE |  | Element type number associated with the area. |
| REAL |  | Real constant set number associated with the area. |
| ESYS |  | Element coordinate system associated with the area. |
| SECN |  | Section number associated with the area. |
| ACCA |  | Concatenated areas (selects only areas that were created by area concatenation ( [[accat\|ACCAT]] )). |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASEL.html
