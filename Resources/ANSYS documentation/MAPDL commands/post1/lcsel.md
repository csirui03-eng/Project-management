---
apdl: "LCSEL"
method: lcsel
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcsel
generated: 2026-08-22
tags: [mapdl-command]
---

# LCSEL

PyMAPDL: `mapdl.lcsel(type_='', lcmin='', lcmax='', lcinc='', **kwargs)`

Selects a subset of load cases.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set.
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Restore the full set.
- `NONE` - Unselect the full set.
- `INVE` - Invert the current set (selected becomes unselected and vice versa).
- `STAT` - Display the current select status.

**lcmin**: Minimum value of load case pointer range.

**lcmax**: Maximum value of load case pointer range. `LCMAX` defaults to `LCMIN`.

**lcinc**: Value increment within range. Defaults to 1. `LCINC` cannot be negative.

## Notes

Selects a subset of load cases for other operations. For example, to select a new set of load cases based on load cases 1 through 7, use **LCSEL**,S,1,7. The subset is used when the ALL label is entered (or implied) on other commands, such as [[lcfact|LCFACT]], [[lcabs|LCABS]], [[lcoper|LCOPER]], etc. Load cases are flagged as selected and unselected; no load case pointers ( [[lcdef|LCDEF]], [[lcwrite|LCWRITE]], [[lcfile|LCFILE]] ) are actually deleted from the database.

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCSEL.html
