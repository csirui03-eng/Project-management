---
apdl: "COVAL"
method: coval
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.coval
generated: 2026-08-22
tags: [mapdl-command]
---

# COVAL

PyMAPDL: `mapdl.coval(tblno1='', tblno2='', sv1='', sv2='', sv3='', sv4='', sv5='', sv6='', sv7='', **kwargs)`

Defines PSD cospectral values.

## Parameters

**tblno1**: First input PSD table number associated with this spectrum.

**tblno2**: Second input PSD table number associated with this spectrum.

**sv1**, **sv2**, **sv3**, **sv4**, **sv5**, **sv6**, **sv7**: PSD cospectral values corresponding to the frequency points ( [[psdfrq|PSDFRQ]] ).

## Notes

Defines PSD cospectral values to be associated with the previously defined frequency points. Two table references are required since values are off- diagonal terms. Unlike autospectra ( [[psdval|PSDVAL]] ), the cospectra can be positive or negative. The cospectral curve segment where there is a sign change is interpolated linearly (the rest of the curve segments use log-log interpolation). For better accuracy, choose as small a curve segment as possible wherever a sign change occurs.

Repeat **COVAL** command using the same table numbers for additional points. This command is valid for [[spopt|SPOPT]],PSD only.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COVAL.html
