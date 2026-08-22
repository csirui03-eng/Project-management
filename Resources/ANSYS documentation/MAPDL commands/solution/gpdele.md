---
apdl: "GPDELE"
method: gpdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution._gap_conditions.GapConditions.gpdele
generated: 2026-08-22
tags: [mapdl-command]
---

# GPDELE

PyMAPDL: `mapdl.gpdele(gap1='', gap2='', ginc='', **kwargs)`

Deletes gap conditions.

## Parameters

**gap1**, **gap2**, **ginc**: Delete gap conditions from `GAP1` to `GAP2` (defaults to `GAP1` ) in steps of `GINC` (defaults to 1).

## Notes

Deletes gap conditions defined with the [[gp|GP]] command. Gap conditions following those deleted are automatically compressed and renumbered. If used in SOLUTION, this command is valid only within the first load step.

This command is also valid in PREP7.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GPDELE.html
