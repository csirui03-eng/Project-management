---
apdl: "GPLIST"
method: gplist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution._gap_conditions.GapConditions.gplist
generated: 2026-08-22
tags: [mapdl-command]
---

# GPLIST

PyMAPDL: `mapdl.gplist(gap1='', gap2='', ginc='', **kwargs)`

Lists the gap conditions.

## Parameters

**gap1**, **gap2**, **ginc**: List gap conditions from `GAP1` to `GAP2` ( `GAP2` defaults to `GAP1` ) in steps of `GINC` (defaults to 1). If `GAP1` = ALL (default), `GAP2` and `GINC` are ignored and all gap conditions are listed.

## Notes

This command is valid in any processor.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GPLIST.html
