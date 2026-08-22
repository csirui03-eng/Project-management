---
apdl: "SV"
method: sv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.sv
generated: 2026-08-22
tags: [mapdl-command]
---

# SV

PyMAPDL: `mapdl.sv(damp='', sv1='', sv2='', sv3='', sv4='', sv5='', sv6='', sv7='', sv8='', sv9='', **kwargs)`

Defines spectrum values to be associated with frequency points.

## Parameters

**damp**: Damping ratio for this response spectrum curve. If the same as a previously defined curve, the SV values are added to the previous curve. Up to four different curves may be defined, each with a different damping ratio. Damping values must be input in ascending order.

**sv1**, **sv2**, **sv3**, **sv4**, **sv5**, **sv6**, **sv7**, **sv8**, **sv9**: Spectrum values corresponding to the frequency points ( [[freq|FREQ]] ). Values are interpreted as defined with the [[svtyp|SVTYP]] command. SV values should not be zero. Values required outside the frequency range use the extreme input values.

## Notes

Defines the spectrum values to be associated with the previously defined frequency points ( [[freq|FREQ]] ). Applies only to the single-point response spectrum. Damping has no effect on the frequency solution. Damping values are used only to identify SV curves for the mode combinations calculation. Only the curve with the lowest damping value is used in the initial mode coefficient calculation. Use [[stat|STAT]] command to list current spectrum curve values.

Repeat **SV** command for additional SV points (100 maximum per `DAMP` curve). SV values are added to the `DAMP` curve after the last nonzero SV value.

The interpolation method between response spectrum points and curves is specified using `KeyInterp` in the [[svtyp|SVTYP]] command. It is logarithmic by default.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SV.html
