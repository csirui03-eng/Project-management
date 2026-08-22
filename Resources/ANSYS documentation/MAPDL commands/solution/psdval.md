---
apdl: "PSDVAL"
method: psdval
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdval
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDVAL

PyMAPDL: `mapdl.psdval(tblno='', sv1='', sv2='', sv3='', sv4='', sv5='', sv6='', sv7='', **kwargs)`

Defines PSD values.

## Parameters

**tblno**: Input table number being defined.

**sv1**, **sv2**, **sv3**, **sv4**, **sv5**, **sv6**, **sv7**: Spectral values corresponding to the frequency points ( [[psdfrq|PSDFRQ]] ). Values are interpreted as defined with the [[psdunit|PSDUNIT]] command.

## Notes

Defines PSD values to be associated with the previously defined frequency points.

Repeat **PSDVAL** command for additional values, up to the number of frequency points ( [[psdfrq|PSDFRQ]] ). Values are added after the last nonzero value.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDVAL.html
