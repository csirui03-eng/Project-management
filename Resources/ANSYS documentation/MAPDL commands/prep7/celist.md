---
apdl: "CELIST"
method: celist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.celist
generated: 2026-08-22
tags: [mapdl-command]
---

# CELIST

PyMAPDL: `mapdl.celist(neqn1='', neqn2='', ninc='', option='', **kwargs)`

Lists the constraint equations.

## Parameters

**neqn1**, **neqn2**, **ninc**: List constraint equations from `NEQN1` to `NEQN2` (defaults to `NEQN1` ) in steps of `NINC` (defaults to 1). If `NEQN1` = ALL (default), `NEQN2` and `NINC` are ignored and all constraint equations are listed.

**option**

Options for listing constraint equations:

- `ANY` - List equation set if any of the selected nodes are in the set (default). Only externally-generated constraint equations are listed.
- `ALL` - List equation set only if all of the selected nodes are in the set. Only externally- generated constraint equations are listed.
- `INTE` - List internally-generated constraint equations that are associated with MPC-based contact. Constraint equations are listed only if all the nodes in the set are selected.
- `CONV` - Convert internal constraint equations to external constraint equations. Internal constraint equations are converted only if all of the nodes in the set are selected.

## Notes

This command is valid in any processor. However, the INTE and CONV options are only valid in the Solution processor after a [[solve|SOLVE]] command has been issued.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CELIST.html
