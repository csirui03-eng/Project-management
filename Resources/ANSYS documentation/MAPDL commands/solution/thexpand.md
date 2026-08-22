---
apdl: "THEXPAND"
method: thexpand
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.thexpand
generated: 2026-08-22
tags: [mapdl-command]
---

# THEXPAND

PyMAPDL: `mapdl.thexpand(key='', **kwargs)`

Enables or disables thermal loading

## Parameters

**key**

Activation key:

- `ON` - Thermal loading is included in the load vector (default).
- `OFF` - Thermal loading is not included in the load vector.

## Notes

Temperatures applied in the analysis are used by default to evaluate material properties and contribute to the load vector if the temperature does not equal the reference temperature and a coefficient of thermal expansion is specified.

Use **THEXPAND**,OFF to evaluate the material properties but not contribute to the load vector. This capability is particularly useful when performing a harmonic analysis where you do not want to include harmonically varying thermal loads. It is also useful in a modal analysis when computing a modal load vector but excluding the thermal load.

This command is valid for all analysis types except linear perturbation modal and linear perturbation harmonic analyses. For these two linear perturbation analysis types, the program internally sets **THEXPAND**,OFF, and it cannot be set to ON by using this command ( **THEXPAND**,ON is ignored).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_THEXPAND.html
