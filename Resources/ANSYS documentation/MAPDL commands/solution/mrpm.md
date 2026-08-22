---
apdl: "MRPM"
method: mrpm
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.mrpm
generated: 2026-08-22
tags: [mapdl-command]
---

# MRPM

PyMAPDL: `mapdl.mrpm(val1='', **kwargs)`

Defines the revolutions per minute (RPM) for a machine rotation.

## Parameters

**val1**: The RPM value (no default).

## Notes

A different RPM value can be defined at each load step. The RPM value is used to postprocess the equivalent radiated power from the structural surface (the [[pras|PRAS]] and [[plas|PLAS]] commands) or the radiated sound power level (the [[prfar|PRFAR]] and [[plfar|PLFAR]] commands).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MRPM.html
