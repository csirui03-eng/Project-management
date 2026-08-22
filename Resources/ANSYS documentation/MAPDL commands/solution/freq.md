---
apdl: "FREQ"
method: freq
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.spectrum_options.SpectrumOptions.freq
generated: 2026-08-22
tags: [mapdl-command]
---

# FREQ

PyMAPDL: `mapdl.freq(freq1='', freq2='', freq3='', freq4='', freq5='', freq6='', freq7='', freq8='', freq9='', **kwargs)`

Defines the frequency points for the [[sv|SV]] vs. **FREQ** tables.

## Parameters

**freq1**, **freq2**, **freq3**, **freq4**, **freq5**, **freq6**, **freq7**, **freq8**, **freq9**: Frequency points for SV vs. FREQ tables. Values must be in ascending order. `FREQ1` should be greater than zero. Units are cycles/time.

## Notes

Repeat the **FREQ** command for additional frequency points (100 maximum). Values are added after the last nonzero frequency. If all fields ( `FREQ1` - `FREQ9` ) are blank, erase SV vs. FREQ tables.

Frequencies must be in ascending order.

Spectral values are input with the [[sv|SV]] command and interpreted according to the [[svtyp|SVTYP]] command. Applies only to the SPRS (single-point) option of the [[spopt|SPOPT]] command. See the [[spfreq|SPFREQ]] command for frequency input in MPRS (multi-point) analysis.

Use the [[stat|STAT]] command to list current frequency points.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FREQ.html
