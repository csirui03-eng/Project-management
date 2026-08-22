---
apdl: "RAPPND"
method: rappnd
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.rappnd
generated: 2026-08-22
tags: [mapdl-command]
---

# RAPPND

PyMAPDL: `mapdl.rappnd(lstep='', time='', **kwargs)`

Appends results data from the database to the results file.

## Parameters

**lstep**: Load step number to be assigned to the results data set. If it is the same as an existing load step number on the results file, the appended load step will be inaccessible. Defaults to 1.

**time**: Time value to be assigned to the results data set. Defaults to 0.0. A time value greater than the last load step should be used.

## Notes

This command is typically used to append the results from a load case combination to the results file. See the [[lcwrite|LCWRITE]] command to create a separate load case file. Only summable and constant data are written to the results file by default; non-summable data are not written unless requested ( [[lcsum|LCSUM]] command). `RAPPND` should not be used to append results from a harmonic analysis.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RAPPND.html
