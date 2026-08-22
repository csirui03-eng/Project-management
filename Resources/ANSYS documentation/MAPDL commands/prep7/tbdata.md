---
apdl: "TBDATA"
method: tbdata
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbdata
generated: 2026-08-22
tags: [mapdl-command]
---

# TBDATA

PyMAPDL: `mapdl.tbdata(stloc='', c1='', c2='', c3='', c4='', c5='', c6='', **kwargs)`

Defines data for the material data table.

## Parameters

**stloc**, **c1**, **c2**, **c3**, **c4**, **c5**, **c6**: Data values assigned to six locations starting with `STLOC`. If a value is already in this location, it is redefined. A blank value leaves the existing value unchanged.

## Notes

Defines data for the table specified via the most recent [[tb|TB]] command (at the temperature specified via the most recent [[tbtemp|TBTEMP]] or [[tbfield|TBFIELD]] command, if applicable).

The type of data table specified determines the number of data values needed in **TBDATA**. Data values are interpolated for temperatures or other specified field variables that fall between user- defined [[tbtemp|TBTEMP]] or [[tbfield|TBFIELD]] values.

You can specify values for up to six constants per **TBDATA** command. Issue the command multiple times if needed.

Some elements (for example, `SOLID226` ) support tabular input for some linear materials. For a list of elements supporting tabular material properties and associated primary variables, see [Defining Linear Material Properties Using Tabular Input](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/ansmatdeflin.html#fntbdatareqd)

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBDATA.html
