---
apdl: "TRPLIS"
method: trplis
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.trace_points.TracePoints.trplis
generated: 2026-08-22
tags: [mapdl-command]
---

# TRPLIS

PyMAPDL: `mapdl.trplis(ntrp1='', ntrp2='', trpinc='', opt='', **kwargs)`

Lists charged particle trace points.

## Parameters

**ntrp1**, **ntrp2**, **trpinc**: List points from `NTRP1` to `NTRP2` (defaults to `NTRP1` ) in steps of `TRPINC` (defaults to 1). If `NTRP1` = ALL, `NTRP2` and `TRPINC` are ignored and all trace points are listed. If `NTRP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**opt**

`Opt` = LOC lists the trace point number location (X, Y, Z). Default.

`Opt` = PART lists the trace point number particle settings (velocity, charge, mass).

## Notes

Lists the charged particle trace points in the active display coordinate system ( [[dsys|DSYS]] ). Trace points are defined with the [[trpoin|TRPOIN]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRPLIS.html
