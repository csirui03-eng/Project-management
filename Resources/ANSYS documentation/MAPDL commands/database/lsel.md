---
apdl: "LSEL"
method: lsel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.lsel
generated: 2026-08-22
tags: [mapdl-command]
---

# LSEL

PyMAPDL: `mapdl.lsel(type_='', item='', comp='', vmin='', vmax='', vinc='', kswp='', **kwargs)`

Selects a subset of lines.

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

**item**: Label identifying data. Valid item labels are shown in the table below. Some items also require a component label. If `Item` = PICK (or simply "P"), graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). Defaults to LINE.

**comp**: Component of the item (if required). Valid component labels are shown in the table below.

**vmin**: Minimum value of item range. Ranges are line numbers, coordinate values, attribute numbers, etc., as appropriate for the item. If `VMIN` = 0.0, a tolerance of ±1.0E-6 is used, or ±0.005 x `VMIN` if `VMIN` = `VMAX`. A component name (as specified on the [[cm|CM]] command) may also be substituted for `VMIN` ( `VMAX` and `VINC` are ignored). If `Item` = MAT, TYPE, REAL, ESYS, or NDIV and if `VMIN` is positive, the absolute value of `Item` is compared against the range for selection; if `VMIN` is negative, the signed value of `Item` is compared. See the [[llist|LLIST]] command for a discussion of signed attributes.

**vmax**: Maximum value of item range. `VMAX` defaults to `VMIN`.

**vinc**: Value increment within range. Used only with integer ranges (such as for line numbers). Defaults to 1. `VINC` cannot be negative.

**kswp**

Specifies whether only lines are to be selected:

- `0` - Select lines only.
- `1` - Select lines, as well as keypoints, nodes, and elements associated with selected lines. Valid only with `Type` = S.

## Notes

Selects lines based on values of a labeled item and component. For example, to select a new set of lines based on line numbers 1 through 7, use **LSEL**,S,LINE,,1,7. The subset is used when the ALL label is entered (or implied) on other commands, such as [[llist|LLIST]],ALL. Only data identified by line number are selected. Data are flagged as selected and unselected; no data are actually deleted from the database.

If `Item` = LCCA, the command selects only those lines that were created by concatenation. The `KSWP` field is processed, but the `Comp`, `VMIN`, `VMAX`, and `VINC` fields are ignored.

If `Item` = HPT, the command selects only those lines that contain hard points.

`Item` = RADIUS is only valid for lines that are circular arcs.

**LSEL** is valid in any processor.

For selections based on non-integer numbers (coordinates, results, etc.), items that are within the range `VMIN` - `Toler` and `VMAX` + `Toler` are selected. The default tolerance `Toler` is based on the relative values of `VMIN` and `VMAX` as follows:

- If `VMIN` = `VMAX`, `Toler` = 0.005 x `VMIN`.
- If `VMIN` = `VMAX` = 0.0, `Toler` = 1.0E-6.
- If `VMAX` ≠ `VMIN`, `Toler` = 1.0E-8 x ( `VMAX` - `VMIN` ).

Use the [SELTOL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SELTOL.html#SELTOL.menupath) [[seltol|SELTOL]] command to override this default and specify `Toler` explicitly.

### LSEL - Valid Item and Component Labels

Valid Item and Component Labels **LSEL**, `Type, Item, Comp, VMIN, VMAX, VINC, KSWP`

| Item | Comp | Description |
|----|----|----|
| LINE |  | Line number. |
| EXT |  | Line numbers on exterior of selected area (ignore remaining fields). |
| LOC | X,Y,Z | X, Y, or Z center location in the active coordinate system. |
| TAN1 | X,Y,Z | Unit vector component of outward tangent at beginning of line. |
| TAN2 | X,Y,Z | Unit vector component of outward tangent at end of line. |
| NDIV |  | Number of divisions within the line. |
| SPACE |  | Spacing ratio of line divisions. |
| MAT |  | Material number associated with the line. |
| TYPE |  | Element type number associated with the line. |
| REAL |  | Real constant set number associated with the line. |
| ESYS |  | Element coordinate system associated with the line. |
| SEC |  | Cross section ID number. ( [[secnum\|SECNUM]] ) |
| LENGTH |  | Length of the line. |
| RADIUS |  | Radius of the line. |
| HPT |  | Line number (selects only lines with associated hard points). |
| LCCA |  | Concatenated lines (selects only lines that were created by concatenation ( [[lccat\|LCCAT]] )). |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSEL.html
