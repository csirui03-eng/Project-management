---
apdl: "PSDGRAPH"
method: psdgraph
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdgraph
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDGRAPH

PyMAPDL: `mapdl.psdgraph(tblno1='', tblno2='', displaykey='', **kwargs)`

Displays input PSD curves.

## Parameters

**tblno1**: PSD table number to display.

**tblno2**: Second PSD table number to display. `TBLNO2` is used only in conjunction with the [[coval|COVAL]] or the [[qdval|QDVAL]] commands.

**displaykey**

Key to display the points markers and numbering:

- `0` - Display points markers and numbering (default).
- `1` - Display points numbering only.
- `2` - Display points markers only.
- `3` - No points markers or numbering.

## Notes

The input PSD tables are displayed in log-log format as dotted lines. The best-fit curves, used to perform the closed-form integration, are displayed as solid lines. If there is a significant discrepancy between the two, then you should add one or more intermediate points to the table to obtain a better fit.

If `TBLNO2` is zero, blank, or equal to `TBLNO1`, then the autospectra ( [[psdval|PSDVAL]] ) are displayed for `TBLNO1`. If `TBLNO2` is also specified, then the autospectra for `TBLNO1` and `TBLNO2` are displayed, along with the corresponding cospectra ( [[coval|COVAL]] ) and quadspectra ( [[qdval|QDVAL]] ), if they are defined.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDGRAPH.html
