---
apdl: "PSDSPL"
method: psdspl
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdspl
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDSPL

PyMAPDL: `mapdl.psdspl(tblno='', rmin='', rmax='', **kwargs)`

Defines a partially correlated excitation in a PSD analysis.

## Parameters

**tblno**: Input PSD table number defined with [[psdval|PSDVAL]] command.

**rmin**: Minimum distance between excitation points which are partially correlated. Excited nodes closer than `RMIN` will be fully correlated.

**rmax**: Maximum distance between excitation points which are partially correlated. Excited nodes farther apart than `RMAX` will be uncorrelated.

## Notes

Notes Defines a partially correlated excitation in terms of a sphere of influence relating excitation point geometry (in a PSD analysis). If the distance between any two excitation points is less than `RMIN`, then the excitation is fully correlated. If the distance is greater than `RMAX`, then the excitation is uncorrelated. If the distance lies between `RMIN` and `RMAX`, then the excitation is partially correlated with the degree of correlation dependent on the separation distance between the points. This command is not available for a pressure PSD analysis.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDSPL.html
