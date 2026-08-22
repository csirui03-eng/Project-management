---
apdl: "ETLIST"
method: etlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.etlist
generated: 2026-08-22
tags: [mapdl-command]
---

# ETLIST

PyMAPDL: `mapdl.etlist(ityp1='', ityp2='', inc='', **kwargs)`

Lists currently defined element types.

## Parameters

**ityp1**, **ityp2**, **inc**: Lists element types from `ITYP1` to `ITYP2` (defaults to `ITYP1` ) in steps of `INC` (defaults to 1). If `ITYP1` = ALL (default), `ITYP2` and `INC` are ignored and all element types are listed.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ETLIST.html
