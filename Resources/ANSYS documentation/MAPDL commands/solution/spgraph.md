---
apdl: "SPGRAPH"
method: spgraph
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spgraph
generated: 2026-08-22
tags: [mapdl-command]
---

# SPGRAPH

PyMAPDL: `mapdl.spgraph(tblno='', curvno='', curvnobeg='', **kwargs)`

Displays input spectrum curves for MPRS analysis.

## Parameters

**tblno**: Table number to display. Defaults to 1.

**curvno**: Curve number to display. Defaults to none.

**curvnobeg**: Beginning of the curve number range to display. Defaults to 1.

## Notes

You can display up to 10 input spectrum curves ( [[spval|SPVAL]] and [[spfreq|SPFREQ]] commands) with log X scale.

If the input spectrum curves are not associated with a damping value ( [[spdamp|SPDAMP]] command), `CURVNO` and `CURVNOBeg` are not applicable and table `TBLNO` is displayed. Otherwise, specif y `CURVNO` or `CURVNOBeg` :

- if `CURVNO` is used, one curve is displayed.
- if `CURVNOBeg` is used, up to 10 curves are displayed. `CURVNOBeg` is the beginning of the curve number range of interest.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPGRAPH.html
