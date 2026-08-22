---
apdl: "SECFUNCTION"
method: secfunction
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.secfunction
generated: 2026-08-22
tags: [mapdl-command]
---

# SECFUNCTION

PyMAPDL: `mapdl.secfunction(table='', pattern='', **kwargs)`

Specifies shell section thickness as a tabular function.

## Parameters

**table**: Name of table parameter or array parameter for specifying thickness.

**pattern**: Interpretation pattern for array parameters.

## Notes

The **SECFUNCTION** command is associated with the section most recently defined via the [[sectype|SECTYPE]] command.

A table parameter can define tabular thickness as a function of coordinates. Alternatively, you can use an array parameter (indexed by node number) that expresses the function to be mapped. (See `PATTERN` of NOD2 for array content.) Enclose the table or array name in percent signs (%) ( **SECFUNCTION**,`tablename`).

Issue the [[dim|*DIM]] command to define a table or array.

The table or array defines the total shell thickness at any point in space. In multilayered sections, the total thickness and each layer thickness are scaled accordingly.

The [Function Tool](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BASFUNCGRAPH.html) is a convenient way to define your thickness tables.

Refer to the [[dim|*DIM]] command for interpreting a table in a local coordinate system.

When `PATTERN` = NODE, `TABLE` should be a 1D array parameter (indexed by node number) that expresses the function to be mapped.

When `PATTERN` = NOD2, `TABLE` should be a 2D array parameter (where column 1 contains node numbers and column 2 contains the corresponding thicknesses) that expresses the function to be mapped.

Specify `PATTERN` when `TABLE` is an array parameter only (and not when it is a table parameter or a single value).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECFUNCTION.html
