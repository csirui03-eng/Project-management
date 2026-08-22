---
apdl: "MPCOPY"
method: mpcopy
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpcopy
generated: 2026-08-22
tags: [mapdl-command]
---

# MPCOPY

PyMAPDL: `mapdl.mpcopy(matf='', matt='', **kwargs)`

Copies linear material model data from one material reference number to another.

## Parameters

**matf**: Material reference number from where material property data will be copied.

**matt**: Material reference number to where material property data will be copied.

## Notes

The **MPCOPY** command copies linear material properties only, which are all properties defined through the [[mp|MP]] command. If you copy a model that includes both linear and yield behavior constants (for example, a BKIN model), the **MPCOPY** and [[tbcopy|TBCOPY]], ALL commands are used together to copy the entire model. All input data associated with the model is copied, that is, all data defined through the [[mp|MP]] and [[tb|TB]] commands.

Also, if you copy a material model using the [Material Model Interface](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/BAS1matmodifjwf0413001150.html#BAS1mamoimisjwf0414000942) ( Edit\> Copy ), both the commands **MPCOPY** and [[tbcopy|TBCOPY]], ALL are issued, regardless of whether the model includes linear constants only, or if it includes a combination of linear and yield behavior constants.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPCOPY.html
