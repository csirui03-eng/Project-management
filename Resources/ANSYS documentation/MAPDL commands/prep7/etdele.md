---
apdl: "ETDELE"
method: etdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.element_type.ElementType.etdele
generated: 2026-08-22
tags: [mapdl-command]
---

# ETDELE

PyMAPDL: `mapdl.etdele(ityp1='', ityp2='', inc='', **kwargs)`

Deletes element types.

## Parameters

**ityp1**, **ityp2**, **inc**: Deletes element types from `ITYP1` to `ITYP2` (defaults to `ITYP1` ) in steps of `INC` (defaults to 1). If `ITYP1` = ALL, `ITYP2` and `INC` are ignored and all element types are deleted. Element types are defined with the [[et|ET]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ETDELE.html
