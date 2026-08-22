---
apdl: "FILLDATA"
method: filldata
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.filldata
generated: 2026-08-22
tags: [mapdl-command]
---

# FILLDATA

PyMAPDL: `mapdl.filldata(ir='', lstrt='', lstop='', linc='', value='', dval='', **kwargs)`

Fills a variable by a ramp function.

## Parameters

**ir**: Define data table as variable `IR` (2 to `NV` ( [[numvar|NUMVAR]] )).

**lstrt**: Start at location `LSTRT` (defaults to 1).

**lstop**: Stop at location `LSTOP` (defaults to maximum location as determined from data previously stored.

**linc**: Fill every `LINC` location between `LSTRT` and `LSTOP` (defaults to 1).

**value**: Value assigned to location `LSTRT`.

**dval**: Increment value of previous filled location by `DVAL` and assign sum to next location to be filled (may be positive or negative.)

## Notes

Locations may be filled continuously or at regular intervals ( `LINC` ). Previously defined data at a location will be overwritten.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILLDATA.html
