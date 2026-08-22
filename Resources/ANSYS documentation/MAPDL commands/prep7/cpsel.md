---
apdl: "CPSEL"
method: cpsel
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cpsel
generated: 2026-08-22
tags: [mapdl-command]
---

# CPSEL

PyMAPDL: `mapdl.cpsel(type_='', vmin='', vmax='', vinc='', **kwargs)`

Selects coupled degree-of-freedom sets via predefined reference numbers.

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

**vmin**: Minimum value of coupled DOF reference number range.

**vmax**: Maximum value of coupled DOF reference number range. `VMAX` defaults to `VMIN`.

**vinc**: Value increment within the specified range. Defaults to 1.

## Notes

The **CPSEL** command selects coupled degree-of-freedom sets ( [[cp|CP]] ) via specified reference numbers. `VMIN`, `VMAX`, and `VINC` must be positive integer values.

For example, the following command selects a new set of coupled degree-of-freedom sets based on reference numbers 1 through 7:

``` apdl
CPSEL,S,,,1,7,1
```

Data are flagged as selected and unselected; no data are actually deleted from the database.

Use [[cplist|CPLIST]] to list coupled degree-of-freedom sets and their reference numbers. If a coupled degree-of-freedom set is selected but involves unselected nodes, that coupled degree-of-freedom set will not be listed by the [[cplist|CPLIST]] command, and the solver ignores it.

Internally coupled degrees of freedom are not affected by this command.

This command is also valid in POST1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPSEL.html
