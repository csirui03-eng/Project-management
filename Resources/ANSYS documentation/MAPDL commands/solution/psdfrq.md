---
apdl: "PSDFRQ"
method: psdfrq
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.psdfrq
generated: 2026-08-22
tags: [mapdl-command]
---

# PSDFRQ

PyMAPDL: `mapdl.psdfrq(tblno1='', tblno2='', freq1='', freq2='', freq3='', freq4='', freq5='', freq6='', freq7='', **kwargs)`

Defines the frequency points for the input spectrum tables PSDVAL vs. PSDFRQ for PSD analysis.

## Parameters

**tblno1**: Input table number. When used with the [[coval|COVAL]] or the [[qdval|QDVAL]] command, `TBLNO1` represents the row number of this table. Up to 200 tables may be defined.

**tblno2**: Input table number. `TBLNO2` is used only for the [[coval|COVAL]] or the [[qdval|QDVAL]] commands and represents the column number of this table.

**freq1**, **freq2**, **freq3**, **freq4**, **freq5**, **freq6**, **freq7**: Frequency points (cycles/time) for spectrum vs. frequency tables. `FREQ1` should be greater than zero, and values must be in ascending order. Log-log interpolation will be used between frequency points.

## Notes

The spectrum values may be input with the [[psdval|PSDVAL]], [[coval|COVAL]], or [[qdval|QDVAL]] commands. A separate **PSDFRQ** command must be used for each table and cross table defined. Frequencies must be in ascending order.

Repeat **PSDFRQ** command for additional frequency points. Values are added after the last nonzero frequency. If all fields after **PSDFRQ** are blank, all input vs. frequency tables are erased. If `TBLNO1` is nonblank, all corresponding [[psdval|PSDVAL]] tables are erased. If both `TBLNO1` and `TBLNO2` are nonblank, all corresponding [[coval|COVAL]] and [[qdval|QDVAL]] tables are erased.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSDFRQ.html
