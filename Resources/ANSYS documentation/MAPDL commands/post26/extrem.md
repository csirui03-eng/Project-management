---
apdl: "EXTREM"
method: extrem
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.listing.Listing.extrem
generated: 2026-08-22
tags: [mapdl-command]
---

# EXTREM

PyMAPDL: `mapdl.extrem(nvar1='', nvar2='', ninc='', **kwargs)`

Lists the extreme values for variables.

## Parameters

**nvar1**, **nvar2**, **ninc**: List extremes for variables `NVAR1` through `NVAR2` in steps of `NINC`. Variable range defaults to its maximum. `NINC` defaults to 1.

## Notes

Lists the extreme values (and the corresponding times) for stored and calculated variables. Extremes for stored variables are automatically listed as they are stored. Only the real part of a complex number is used. Extreme values may also be assigned to parameters ( [[get|*GET]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXTREM.html
