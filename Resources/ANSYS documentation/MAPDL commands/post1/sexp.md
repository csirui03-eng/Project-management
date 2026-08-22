---
apdl: "SEXP"
method: sexp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.sexp
generated: 2026-08-22
tags: [mapdl-command]
---

# SEXP

PyMAPDL: `mapdl.sexp(labr='', lab1='', lab2='', exp1='', exp2='', **kwargs)`

Forms an element table item by exponentiating and multiplying.

## Parameters

**labr**: Label assigned to results. If same as existing label, the existing values will be overwritten by these results.

**lab1**: First labeled result item in operation.

**lab2**: Second labeled result item in operation (may be blank).

**exp1**: Exponent applied to `Lab1`.

**exp2**: Exponent applied to `Lab2`.

## Notes

Forms a labeled result item (see [[etable|ETABLE]] command) for the selected elements by exponentiating and multiplying two existing labeled result items according to the operation:

`LabR` = (\| `Lab1` \| <sup>EXP1</sup> ) x (\| `Lab2` \| <sup>EXP2</sup> )

Roots, reciprocals, and divides may also be done with this command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SEXP.html
