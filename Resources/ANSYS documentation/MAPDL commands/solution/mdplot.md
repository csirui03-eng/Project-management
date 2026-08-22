---
apdl: "MDPLOT"
method: mdplot
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.mdplot
generated: 2026-08-22
tags: [mapdl-command]
---

# MDPLOT

PyMAPDL: `mapdl.mdplot(function='', dmpname='', scale='', **kwargs)`

Plots frequency-dependent modal damping coefficients calculated by DMPEXT.

## Parameters

**function**

Function to display.

- `d_coeff` - Damping coefficient
- `s_coeff` - Squeeze coefficient
- `d_ratio` - Damping ratio
- `s_ratio` - Squeeze stiffness ratio

**dmpname**: Array parameter name where damping information is stored. Defaults to `d_damp`.

**scale**

Indicates whether to perform a linear or a double logarithmic plot.

- `LIN` - Perform a linear plot. Default
- `LOG` - Perform a double logarithmic plot.

## Notes

See Thin Film Analysis for more information on thin film analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MDPLOT.html
