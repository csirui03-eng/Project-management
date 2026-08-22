---
apdl: "TBCOPY"
method: tbcopy
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbcopy
generated: 2026-08-22
tags: [mapdl-command]
---

# TBCOPY

PyMAPDL: `mapdl.tbcopy(lab='', matf='', matt='', **kwargs)`

Copies a data table from one material to another.

## Parameters

**lab**: Data table label. See the [[tb|TB]] command for valid labels, and see [[tbcopy#Notes|TBCOPY]] for `Lab` = ALL.

**matf**: Material reference number where data table is to be copied from.

**matt**: Material reference number where data table is to be copied to.

## Notes

The **TBCOPY** command, with `Lab` = ALL, copies all of the nonlinear data defined by the [[tb|TB]] command. If you copy a model that includes both yield behavior constants and linear constants (for example, a BKIN model), **TBCOPY**,ALL and [[mpcopy|MPCOPY]] are used together to copy the entire model. All input data associated with the model is copied, that is, all data defined through the [[tb|TB]] and [[mp|MP]] commands.

Also, if you copy a material model using the [Material Model Interface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/BAS1matmodifjwf0413001150.html#BAS1mamoimisjwf0414000942) ( Edit\> Copy ), both the commands **TBCOPY**,ALL and [[mpcopy|MPCOPY]] are issued, regardless of whether the model includes linear constants only, or if it includes a combination of linear and yield behavior constants.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBCOPY.html
