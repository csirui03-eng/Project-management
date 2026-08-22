---
apdl: "MPPLOT"
method: mpplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mpplot
generated: 2026-08-22
tags: [mapdl-command]
---

# MPPLOT

PyMAPDL: `mapdl.mpplot(lab='', mat='', tmin='', tmax='', pmin='', pmax='', **kwargs)`

Plots linear material properties as a function of temperature.

## Parameters

**lab**: Linear material property label (EX, EY, etc.) ( [[mp|MP]] ).

**mat**: Material reference number. Defaults to 1.

**tmin**: Minimum abscissa value to be displayed.

**tmax**: Maximum abscissa value.

**pmin**: Minimum property (ordinate) value to be displayed.

**pmax**: Maximum property value.

## Notes

When the property is from tables, the **MPPLOT** command will not be valid because the property could be a f unction of more than temperature.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPPLOT.html
