---
apdl: "SVPLOT"
method: svplot
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.svplot
generated: 2026-08-22
tags: [mapdl-command]
---

# SVPLOT

PyMAPDL: `mapdl.svplot(optionscale='', damp1='', damp2='', damp3='', damp4='', **kwargs)`

Displays input spectrum curves.

## Parameters

**optionscale**

Flag to activate or deactivate input spectrum value scaling:

- `OFF` - Do not scale the input spectrum values with scale factor FACT ( [[svtyp|SVTYP]] command). This is the default value.
- `ON` - Scale the input spectrum values with scale factor FACT ( [[svtyp|SVTYP]] command)

**damp1**: Damping ratio corresponding to DAMP ( [[sv|SV]] command) defining the first spectrum curve.

**damp2**: Damping ratio corresponding to DAMP ( [[sv|SV]] command) defining the second spectrum curve.

**damp3**: Damping ratio corresponding to DAMP ( [[sv|SV]] command) defining the third spectrum curve.

**damp4**: Damping ratio corresponding to DAMP ( [[sv|SV]] command) defining the fourth spectrum curve.

## Notes

You can display up to four input spectrum tables ( [[sv|SV]] and [[freq|FREQ]] commands) with log X scale. If no damping ratio is specified, all spectrum tables are displayed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/None
