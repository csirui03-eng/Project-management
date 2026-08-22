---
apdl: "LPLOT"
method: lplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lplot
generated: 2026-08-22
tags: [mapdl-command]
---

# LPLOT

PyMAPDL: `mapdl.lplot(nl1='', nl2='', ninc='', **kwargs)`

PyMAPDL overrides `mapdl.lplot` with its own wrapper, so the signature above is not what `mapdl.lplot` runs. Reach the APDL command as text: `mapdl.run("LPLOT,...")`.

Displays the selected lines.

## Parameters

**nl1**, **nl2**, **ninc**: Display lines from `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL (default), `NL2` and `NINC` are ignored and display all selected lines ( [[lsel|LSEL]] ).

## Notes

Mesh divisions on plotted lines are controlled by the `LDIV` option of the [[psymb|/PSYMB]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LPLOT.html
