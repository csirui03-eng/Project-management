---
apdl: "ESEL"
method: esel
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.esel
generated: 2026-08-22
tags: [mapdl-command]
---

# ESEL

PyMAPDL: `mapdl.esel(type_='', item='', comp='', vmin='', vmax='', vinc='', kabs='', **kwargs)`

Selects a subset of elements.

**Command default:**

All elements are selected.

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

**item**: Label identifying data, see *ESEL - Valid Item and Component Labels*. Some items also require a component label. If `Item` = PICK (or simply "P"), graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). Defaults to ELEM. If `Item` = STRA (straightened), elements are selected whose midside nodes do not conform to the curved line or non-flat area on which they should lie. (Such elements are sometimes formed during volume meshing ( [[vmesh|VMESH]] ) in an attempt to avoid excessive element distortion.) You should graphically examine any such elements to evaluate their possible effect on solution accuracy.

**comp**: Component of the item (if required). Valid component labels are shown in *ESEL - Valid Item and Component Labels* below.

**vmin**: Minimum value of item range. Ranges are element numbers, attribute numbers, load values, or result values as appropriate for the item. A component name (as specified via the [[cm|CM]] command) can also be substituted for `VMIN` (in which case `VMAX` and `VINC` are ignored).

**vmax**

Maximum value of item range. `VMAX` defaults to `VMIN` for input values.

For result values, `VMAX` defaults to infinity if `VMIN` is positive, or to zero if `VMIN` is negative.

**vinc**: Value increment within range. Used only with integer ranges (such as for element and attribute numbers). Defaults to 1. `VINC` cannot be negative.

**kabs**

Absolute value key:

- `0` - Check sign of value during selection.
- `1` - Use absolute value during selection (sign ignored).

## Notes

Selects elements based on values of a labeled item and component. For example, to select a new set of elements based on element numbers 1 through 7, use **ESEL**,S,ELEM,,1,7. The subset is used when the ALL label is entered (or implied) on other commands, such as [[elist|ELIST]],ALL. Only data identified by element number are selected. Selected data are internally flagged; no actual removal of data from the database occurs. Different element subsets cannot be used for different load steps ( [[solve|SOLVE]] ) in a [[slashsolu|/SOLU]] sequence. The subset used in the first load step is used for all subsequent load steps regardless of subsequent **ESEL** specifications.

This command is valid in any processor.

Elements crossing the named path ( [[path|PATH]] ) are selected. This option is available only in PREP7 and POST1. If no geometry data has been mapped to the path (via [[pmap|PMAP]] and [[pdef|PDEF]], for example), the path assumes the default mapping option ( [[pmap|PMAP]],UNIFORM) to map the geometry prior to selecting the elements. If an invalid path name is given, the **ESEL** command is ignored (and the status of selected elements is unchanged). If no elements are crossing the path, the **ESEL** command returns zero elements selected.

For selections based on non-integer numbers (coordinates, results, etc.), items that are within the range `VMIN` - `Toler` and `VMAX` + `Toler` are selected. The default tolerance `Toler` is based on the relative values of `VMIN` and `VMAX` as follows:

- If `VMIN` = `VMAX`, `Toler` = 0.005 x `VMIN`.
- If `VMIN` = `VMAX` = 0.0, `Toler` = 1.0E-6.
- If `VMAX` ≠ `VMIN`, `Toler` = 1.0E-8 x ( `VMAX` - `VMIN` ).

To override this default and specify `Toler` explicitly, issue the [SELTOL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_SELTOL.html#SELTOL.menupath) [[seltol|SELTOL]] command.

### ESEL - Valid Item and Component Labels

Valid Item and Component Labels **ESEL**, `Type, Item, Comp, VMIN, VMAX, VINC, KABS`

| Item | Comp | Description |
|----|----|----|
| ELEM |  | Element number. |
| ADJ |  | Elements adjacent to element `VMIN` ( `VMAX` and `VINC` fields are ignored). Only elements (of the same dimensionality) adjacent to lateral faces are considered. Progression continues until edge of model or until more than two elements are adjacent at a face. |
| CENT | X, Y, Z | X, Y, or Z location in the active coordinate system. |
| TYPE |  | Element type number. |
| ENAME |  | Element name (or identifying number). |
| MAT |  | Material ID number. |
| REAL | (blank) | Real constant number. |
| ESYS |  | Element coordinate system number. |
| OVER |  | Overlapping contact elements created during contact pair splitting ( [[cncheck\|CNCHECK]],SPLIT/DMP) |
| LIVE |  | Active elements ( [[ealive\|EALIVE]] ). `VMIN` and `VMAX` fields are ignored. |
| LAYER |  | Layer number (where only composite elements with a nonzero thickness for the requested layer number are included) ( [[layer\|LAYER]] ). |
| SEC | (blank) | Cross section ID number ( [[secnum\|SECNUM]] ) |
| STRA |  | Straightened. See the description of the `Item` argument above. |
| SFE | PRES | Element pressure. |
| BFE | TEMP | Element temperature. |
| PATH | `Lab` | Selects all elements being crossed by the path with name `Lab` ( [[path\|PATH]] ). If `Lab` = ALL, all elements related to all defined paths are selected. |
| Valid item and component labels for element result values are: |  |  |
| ETAB | `Lab` | Any user-defined element table label ( [[etable\|ETABLE]] ). |

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESEL.html
