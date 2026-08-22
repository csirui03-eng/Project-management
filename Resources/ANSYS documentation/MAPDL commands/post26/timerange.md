---
apdl: "TIMERANGE"
method: timerange
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.timerange
generated: 2026-08-22
tags: [mapdl-command]
---

# TIMERANGE

PyMAPDL: `mapdl.timerange(tmin='', tmax='', **kwargs)`

Specifies the time range for which data are to be stored.

## Parameters

**tmin**: Minimum time (defaults to first time (or frequency) point on the file).

**tmax**: Maximum time (defaults to last time (or frequency) point on the file).

## Notes

Defines the time (or frequency) range for which data are to be read from the file and stored in memory. Use the [[nstore|NSTORE]] command to define the time increment.

Use [[prtime|PRTIME]] or [[pltime|PLTIME]] to specify the time (frequency) range for cyclic mode- superposition harmonic analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TIMERANGE.html
