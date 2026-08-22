---
apdl: "SPVAL"
method: spval
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spval
generated: 2026-08-22
tags: [mapdl-command]
---

# SPVAL

PyMAPDL: `mapdl.spval(tblno='', curvno='', sv1='', sv2='', sv3='', sv4='', sv5='', sv6='', sv7='', **kwargs)`

Defines multi-point response spectrum values.

## Parameters

**tblno**: Input table number. It corresponds to `TBLNO` on the [[spfreq|SPFREQ]] command.

**curvno**: Input curve number. It corresponds to `CURVNO` on the [[spdamp|SPDAMP]] command (optional).

**sv1**, **sv2**, **sv3**, **sv4**, **sv5**, **sv6**, **sv7**: Spectral values corresponding to the frequency points ( [[spfreq|SPFREQ]] ) and damping ratio ( [[spdamp|SPDAMP]] ). Values are interpreted as defined with the [[spunit|SPUNIT]] command.

## Notes

Notes Defines multi-point response spectrum values to be associated with the previously defined frequency points ( [[spfreq|SPFREQ]] ). It can also be associated with the previously defined damping value ( [[spdamp|SPDAMP]] ). If `CURVNO` is not specified, the input spectrum is not associated with a damping value.

Repeat **SPVAL** command for additional values, up to the number of frequency points ( [[spfreq|SPFREQ]] ). Values are added after the last nonzero value.

The interpolation method between response spectrum points and curves is specified using `KeyInterp` on the [[spunit|SPUNIT]] command. It is logarithmic by default.

Use the [[sptopt|SPTOPT]] and [[stat|STAT]] commands to list current spectrum curve values.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPVAL.html
