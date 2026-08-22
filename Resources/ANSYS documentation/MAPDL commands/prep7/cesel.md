---
apdl: "CESEL"
method: cesel
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.cesel
generated: 2026-08-22
tags: [mapdl-command]
---

# CESEL

PyMAPDL: `mapdl.cesel(type_='', vmin='', vmax='', vinc='', **kwargs)`

Selects constraint equations via predefined reference numbers.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new set (default).
- `A` - Select an additional set and add it to the current set.
- `U` - Unselect a set from the current set.
- `ALL` - Restore the full set.
- `NONE` - Unselect the full set.
- `INVE` - Invert the current set (selected becomes unselected and vice versa).
- `STAT` - Display the current select status.

**vmin**: Minimum value of constraint equation reference number range.

**vmax**: Maximum value of constraint equation reference number range. `VMAX` defaults to `VMIN`.

**vinc**: Value increment within the specified range. Defaults to 1.

## Notes

The **CESEL** command selects sets of constraint equations ( [[ce|CE]] ) via specified reference numbers. `VMIN`, `VMAX`, and `VINC` must be positive integer values.

For example, the following command selects a new set of constraint equations based on reference numbers 1 through 7:

``` apdl
CESEL,S,,,1,7,1
```

Data are flagged as selected and unselected; no data are actually deleted from the database.

Use [[celist|CELIST]] to list constraint equations and their reference numbers. If a constraint equation is selected but involves unselected nodes, that constraint equation will not be listed by the [[celist|CELIST]] command, and the solver ignores it.

Internal constraint equations are not affected by this command.

This command is also valid in POST1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CESEL.html
