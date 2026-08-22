---
apdl: "EMSEL"
method: emsel
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.emsel
generated: 2026-08-22
tags: [mapdl-command]
---

# EMSEL

PyMAPDL: `mapdl.emsel(type_='', vmin='', vmax='', vinc='', **kwargs)`

Selects a group of [reinforcing](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_compreinfdirectemb.html) members via a predefined global identifier.

## Parameters

**type_**

Specifies the selection type for the reinforcing elements:

- S - Select a new set (default).
- A - Select an additional set and add it to the current set.
- U - Unselect a set from the current set.
- ALL - Restore the full set.
- STAT - Display the current selection status.

The following arguments are valid only when `Type` = S, A, or U:

**vmin**: Minimum value of a group-identifier range.

**vmax**: Maximum value of global identifier range. Default = VMIN for input values.

**vinc**: Value increment within the specified range. Default = 1.

## Notes

Understanding Reinforcing Member Groups When using the [mesh-independent method](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#) for defining reinforcing, the global identifier for a set of `MESH200` elements (specified via [[egid|EGID]] ) is transferred from the `MESH200` elements to the reinforcing members (individual reinforcings) when the reinforcing elements (REINF `nnn` ) are generated ( [[ereinf|EREINF]] ).

The **EMSEL** command selects groups of reinforcing members (individual reinforcings) via specified global identifiers.

> **Example: Selecting Reinforcing Member Groups**
>
> The following command selects a new group of reinforcing members based on global identifiers 1 through 7:
>
> ``` apdl
> EMSEL,S,,,1,7
> ```

`VMIN`, `VMAX`, and `VINC` are positive integer values.

This command is valid in PREP7 and POST1.

For more information about using this command in a mesh-independent reinforcing analysis, see [Selecting and Displaying Groups of Reinforcing Members](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strreinfworkflow.html#)

(table not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMSEL.html
