---
apdl: "SSLN"
method: ssln
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ssln
generated: 2026-08-22
tags: [mapdl-command]
---

# SSLN

PyMAPDL: `mapdl.ssln(fact='', size='', **kwargs)`

Selects and displays small lines in the model.

## Parameters

**fact**: Factor used to determine small lines. `FACT` times the average line length in the model is used as the line length limit below which lines will be selected.

**size**: Line length limit for line selection. Lines that have a length less than or equal to `SIZE` will be selected. Used only if `FACT` is blank.

## Notes

**SSLN** invokes a predefined Mechanical APDL macro for selecting small lines in a model. Lines that are smaller than or equal to the specified limit ( `FACT` or `SIZE` ) are selected and line numbers are displayed. This command macro is useful for detecting very small lines in a model that may cause problems (that is, poorly shaped elements or a meshing failure) during meshing. All lines that are not "small" will be unselected and can be reselected with the [[lsel|LSEL]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSLN.html
