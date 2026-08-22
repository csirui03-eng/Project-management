---
apdl: "CESGEN"
method: cesgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.constraint_equations.ConstraintEquations.cesgen
generated: 2026-08-22
tags: [mapdl-command]
---

# CESGEN

PyMAPDL: `mapdl.cesgen(itime='', inc='', nset1='', nset2='', ninc='', **kwargs)`

Generates a set of constraint equations from existing sets.

## Parameters

**itime**, **inc**: Do this generation operation a total of `ITIME` s, incrementing all nodes in the existing sets by `INC` each time after the first. `ITIME` must be \>1 for generation to occur.

**nset1**, **nset2**, **ninc**: Generate sets from sets beginning with `NSET1` to `NSET2` (defaults to `NSET1` ) in steps of `NINC` (defaults to 1). If `NSET1` is negative, `NSET2` and `NINC` are ignored and the last \| `NSET1` \| sets (in sequence from maximum set number) are used as the sets to be repeated.

## Notes

Generates additional sets of constraint equations (with same labels) from existing sets. Node numbers between sets may be uniformly incremented.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CESGEN.html
