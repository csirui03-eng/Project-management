---
apdl: "SUEVAL"
method: sueval
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.sueval
generated: 2026-08-22
tags: [mapdl-command]
---

# SUEVAL

PyMAPDL: `mapdl.sueval(parm='', lab1='', oper='', **kwargs)`

Perform operations on a mapped item and store result in a scalar parameter.

## Parameters

**parm**: APDL parameter name.

**lab1**: Eight character set name for the first set used in calculation.

**oper**

Operation to perform:

- `SUM` - Sum of `lab1` result values.
- `INTG` - Integral of `lab1` over surface.
- `AVG` - Area-weighted average of a result item \[Σ( `lab1` \*DA) / Σ(DA)\]

## Notes

The result of this operation is a scalar APDL parameter value. If multiple surfaces are selected when this command is issued, then the operation is carried out on each surface individually and the parameter represents the cumulative value of the operation on all selected surfaces.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUEVAL.html
