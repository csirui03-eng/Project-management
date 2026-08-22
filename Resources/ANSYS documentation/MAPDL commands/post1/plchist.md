---
apdl: "PLCHIST"
method: plchist
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plchist
generated: 2026-08-22
tags: [mapdl-command]
---

# PLCHIST

PyMAPDL: `mapdl.plchist(spec='', freqpt='', **kwargs)`

Plots a histogram of the frequency response of each sector for the given [[cycspec|CYCSPEC]] specification.

## Parameters

**spec**: [[cycspec|CYCSPEC]] specification number (ordered 1 to N in the order input; use [[cycspec|CYCSPEC]],LIST to view the current list order). Defaults to 1.

**freqpt**: Harmonic frequency point to plot (the data set number NSET or CUMULATIVE on [[set|SET]],LIST). Defaults to the current [[set|SET]] frequency.

## Notes

Following a cyclic mode-superposition harmonic analysis, this command creates a histogram plot of the result item given by a [[cycspec|CYCSPEC]] specification versus the sector number. A [[cyccalc|CYCCALC]] command must have been issued prior to this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLCHIST.html
