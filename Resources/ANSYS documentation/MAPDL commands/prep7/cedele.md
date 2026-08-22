---
apdl: "CEDELE"
method: cedele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.cedele
generated: 2026-08-22
tags: [mapdl-command]
---

# CEDELE

PyMAPDL: `mapdl.cedele(neqn1='', neqn2='', ninc='', nsel='', **kwargs)`

Deletes constraint equations.

## Parameters

**neqn1**, **neqn2**, **ninc**: Delete constraint equations from `NEQN1` to `NEQN2` (defaults to `NEQN1` ) in steps of `NINC` (defaults to 1). If `NEQN1` = ALL, `NEQN2` and `NINC` will be ignored all constraint equations will be deleted.

**nsel**

Additional node selection control:

- `ANY` - Delete equation set if any of the selected nodes are in the set (default).
- `ALL` - Delete equation set only if all of the selected nodes are in the set.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CEDELE.html
