---
apdl: "CSLIST"
method: cslist
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.cslist
generated: 2026-08-22
tags: [mapdl-command]
---

# CSLIST

PyMAPDL: `mapdl.cslist(kcn1='', kcn2='', kcinc='', **kwargs)`

Lists coordinate systems.

## Parameters

**kcn1**, **kcn2**, **kcinc**: List coordinate systems from `KCN1` to `KCN2` (defaults to `KCN1` ) in steps of `KCINC` (defaults to 1). If `KCN1` = ALL (default), `KCN2` and `KCINC` are ignored and all coordinate systems are listed.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CSLIST.html
