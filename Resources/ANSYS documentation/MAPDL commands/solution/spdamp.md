---
apdl: "SPDAMP"
method: spdamp
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spdamp
generated: 2026-08-22
tags: [mapdl-command]
---

# SPDAMP

PyMAPDL: `mapdl.spdamp(tblno='', curvno='', dampratio='', **kwargs)`

Defines input spectrum damping in a multi-point response spectrum analysis.

## Parameters

**tblno**: Input table number. Corresponds to the frequency table number ( `TBLNO` on the [[spfreq|SPFREQ]] command).

**curvno**: Input curve number. Corresponds to the spectrum values curve number ( `CURVNO` on the [[spval|SPVAL]] command).

**dampratio**: Damping ratio for the response spectrum curve. Up to 20 different curves may be defined, each with a different damping ratio. Damping values must be input in ascending order.

## Notes

Defines multi-point response spectrum damping value to be associated with:

- Previously defined frequency points ( [[spfreq|SPFREQ]] ).
- Subsequently defined spectrum points ( [[spval|SPVAL]] ).

Damping values are used only to identify input spectrum values for the mode coefficients calculation.

The curve number must be input in ascending order starting with 1.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPDAMP.html
