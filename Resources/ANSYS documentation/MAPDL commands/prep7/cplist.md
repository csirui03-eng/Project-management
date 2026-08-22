---
apdl: "CPLIST"
method: cplist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.coupled_dof.CoupledDof.cplist
generated: 2026-08-22
tags: [mapdl-command]
---

# CPLIST

PyMAPDL: `mapdl.cplist(nset1='', nset2='', ninc='', nsel='', **kwargs)`

Lists the coupled degree of freedom sets.

## Parameters

**nset1**, **nset2**, **ninc**: List coupled sets from `NSET1` to `NSET2` (defaults to `NSET1` ) in steps of `NINC` (defaults to 1). If `NSET1` = ALL (default), `NSET2` and `NINC` are ignored and all coupled sets are listed.

**nsel**

Node selection control:

- `ANY` - List coupled set if any of the selected nodes are in the set (default).
- `ALL` - List coupled set only if all of the selected nodes are in the set.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CPLIST.html
