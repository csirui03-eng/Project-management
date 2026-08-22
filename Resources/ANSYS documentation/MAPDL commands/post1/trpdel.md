---
apdl: "TRPDEL"
method: trpdel
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.trace_points.TracePoints.trpdel
generated: 2026-08-22
tags: [mapdl-command]
---

# TRPDEL

PyMAPDL: `mapdl.trpdel(ntrp1='', ntrp2='', trpinc='', **kwargs)`

Deletes charged particle trace points.

## Parameters

**ntrp1**, **ntrp2**, **trpinc**: Delete points from `NTRP1` to `NTRP2` (defaults to `NTRP1` ) in steps of `TRPINC` (defaults to 1). If `NTRP1` = ALL, `NTRP2` and `TRPINC` are ignored and all trace points are deleted. If `NTRP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Deletes charged particle trace points defined with the [[trpoin|TRPOIN]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRPDEL.html
