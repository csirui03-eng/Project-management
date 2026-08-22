---
apdl: "*TAXIS"
method: taxis
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.taxis
generated: 2026-08-22
tags: [mapdl-command]
---

# *TAXIS

PyMAPDL: `mapdl.taxis(parmloc='', naxis='', val1='', val2='', val3='', val4='', val5='', val6='', val7='', val8='', val9='', val10='', **kwargs)`

Defines table index numbers.

## Parameters

**parmloc**: Name and starting location in the table array parameter for indexing. Indexing occurs along the axis defined with `nAxis`.

**naxis**

Axis along which indexing occurs. Valid labels are:

- `1` - Corresponds to Row. Default.
- `2` - Corresponds to Column.
- `3` - Corresponds to Plane.
- `4` - Corresponds to Book.
- `5` - Corresponds to Shelf.
- `ALL` - Lists all index numbers. Valid only if `Val1` = LIST.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**, **val7**, **val8**, **val9**, **val10**

Values of the index numbers for the axis `nAxis`, starting from the table array parameter location `ParmLoc`. You can define up to ten values.

To list the index values specified with `nAxis`, issue `Val1` = LIST. If `Val1` = LIST, `Val2` - `Val10` are ignored.

## Notes

**\*TAXIS** is a convenient method to define table index values. These values reside in the zero column, row, etc. Instead of filling values in these zero location spots, use the **\*TAXIS** command. For example,

``` apdl
*TAXIS,longtable(1,4,1,1),2,1.0,2.2,3.5,4.7,5.9
```

would fill index values 1.0, 2.2, 3.5, 4.7, and 5.9 in `nAxis` 2 (column location), starting at location 4.

To list index numbers, issue **\*TAXIS**, `ParmLoc`, `nAxis`, LIST, where `nAxis` = 1 through 5 or ALL.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TAXIS.html
