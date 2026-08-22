---
apdl: "PRTIME"
method: prtime
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.listing.Listing.prtime
generated: 2026-08-22
tags: [mapdl-command]
---

# PRTIME

PyMAPDL: `mapdl.prtime(tmin='', tmax='', **kwargs)`

Defines the time range for which data are to be listed.

**Command default:**

Use the previously defined range ( [[timerange|TIMERANGE]] ).

## Parameters

**tmin**: Minimum time (defaults to the first point stored).

**tmax**: Maximum time (defaults to the last point stored).

## Notes

Defines the time (or frequency) range (within the range stored) for which data are to be listed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRTIME.html
