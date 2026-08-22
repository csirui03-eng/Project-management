---
apdl: "PLCFREQ"
method: plcfreq
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plcfreq
generated: 2026-08-22
tags: [mapdl-command]
---

# PLCFREQ

PyMAPDL: `mapdl.plcfreq(spec='', sectbeg='', sectend='', **kwargs)`

Plots the frequency response for the given [[cycspec|CYCSPEC]] specification.

## Parameters

**spec**: [[cycspec|CYCSPEC]] specification number (ordered 1 to N in the order input; use [[cycspec|CYCSPEC]],LIST to view the current list order). Defaults to 1.

**sectbeg**: Beginning sector number to plot. Defaults to 1.

**sectend**: Ending sector number to plot. Defaults to the total number of sectors expanded ( [[cycexpand|/CYCEXPAND]] ).

## Notes

Following a cyclic mode-superposition harmonic analysis, this command plots the result item given by a [[cycspec|CYCSPEC]] specification versus the harmonic frequency, one curve for each of the specified sectors. A [[cyccalc|CYCCALC]] command must have been issued prior to this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLCFREQ.html
