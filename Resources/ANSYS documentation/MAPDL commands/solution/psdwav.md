---
apdl: "PSDWAV"
method: psdwav
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdwav
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDWAV

PyMAPDL: `mapdl.psdwav(tblno='', vx='', vy='', vz='', **kwargs)`

Defines a wave propagation excitation in a PSD analysis.

## Parameters

**tblno**: Input PSD table number defined with [[psdval|PSDVAL]] command.

**vx**: Global Cartesian X-velocity of traveling wave.

**vy**: Global Cartesian Y-velocity of traveling wave.

**vz**: Global Cartesian Z-velocity of traveling wave.

## Notes

Defines a traveling wave in a PSD analysis. This command is not available for a pressure PSD analysis.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDWAV.html
