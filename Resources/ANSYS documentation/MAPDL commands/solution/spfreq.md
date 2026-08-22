---
apdl: "SPFREQ"
method: spfreq
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.spfreq
generated: 2026-08-22
tags: [mapdl-command]
---

# SPFREQ

PyMAPDL: `mapdl.spfreq(tblno='', freq1='', freq2='', freq3='', freq4='', freq5='', freq6='', freq7='', **kwargs)`

Defines the frequency points for the input spectrum tables [[spval|SPVAL]] vs. **SPFREQ** for multi- point spectrum analysis.

## Parameters

**tblno**: Input table number. Up to 200 tables may be defined.

**freq1**, **freq2**, **freq3**, **freq4**, **freq5**, **freq6**, **freq7**: Frequency points (Hz) for spectrum vs. frequency tables. `FREQ1` should be greater than zero, and values must be in ascending order.

## Notes

The spectrum values are input with the [[spval|SPVAL]] command. A separate **SPFREQ** command must be used for each table defined. Frequencies must be in ascending order.

Repeat **SPFREQ** command for additional frequency points. Values are added after the last nonzero frequency.

If all fields after **SPFREQ** are blank, all input vs. frequency tables are erased. If `TBLNO` is the only non-blank field, all corresponding [[spval|SPVAL]] curves are erased.

Use the [[sptopt|SPTOPT]] and [[stat|STAT]] commands to list current frequency points.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPFREQ.html
