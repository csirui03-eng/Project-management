---
apdl: "TBTEMP"
method: tbtemp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbtemp
generated: 2026-08-22
tags: [mapdl-command]
---

# TBTEMP

PyMAPDL: `mapdl.tbtemp(temp='', kmod='', **kwargs)`

Defines a temperature for a material data table.

## Parameters

**temp**: Temperature value (defaults to 0.0 if `KMOD` is blank).

**kmod**: If blank, `TEMP` defines a new temperature. (Issue [[tblist|TBLIST]] to list temperatures and data.)

## Notes

The **TBTEMP** command defines a temperature to be associated with the data on subsequent [[tbpt|TBPT]] or [[tbdata|TBDATA]] commands.

The defined temperature remains active until the next **TBTEMP** command is issued.

Data values must be defined with the temperatures in ascending order.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBTEMP.html
