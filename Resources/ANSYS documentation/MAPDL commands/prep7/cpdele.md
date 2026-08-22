---
apdl: "CPDELE"
method: cpdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cpdele
generated: 2026-08-22
tags: [mapdl-command]
---

# CPDELE

PyMAPDL: `mapdl.cpdele(nset1='', nset2='', ninc='', nsel='', **kwargs)`

Deletes coupled degree of freedom sets.

## Parameters

**nset1**, **nset2**, **ninc**: Delete coupled sets from `NSET1` to `NSET2` (defaults to `NSET1` ) in steps of `NINC` (defaults to 1). If `NSET1` = ALL, `NSET2` and `NINC` are ignored and all coupled sets are deleted.

**nsel**

Additional node selection control:

- `ANY` - Delete coupled set if any of the selected nodes are in the set (default).
- `ALL` - Delete coupled set only if all of the selected nodes are in the set.

## Notes

See the [[cp|CP]] command for a method to delete individual nodes from a set.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPDELE.html
