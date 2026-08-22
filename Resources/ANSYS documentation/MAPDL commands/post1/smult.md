---
apdl: "SMULT"
method: smult
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.smult
generated: 2026-08-22
tags: [mapdl-command]
---

# SMULT

PyMAPDL: `mapdl.smult(labr='', lab1='', lab2='', fact1='', fact2='', **kwargs)`

Forms an element table item by multiplying two other items.

## Parameters

**labr**: Label assigned to results. If same as existing label, the existing values will be overwritten by these results.

**lab1**: First labeled result item in operation.

**lab2**: Second labeled result item in operation (may be blank).

**fact1**: Scale factor applied to `Lab1`. A (blank) or '0' entry defaults to 1.0.

**fact2**: Scale factor applied to `Lab2`. A (blank) or '0' entry defaults to 1.0.

## Notes

Forms a labeled result item (see [[etable|ETABLE]] command) for the selected elements by multiplying two existing labeled result items according to the operation:

`LabR` = ( `FACT1` x `Lab1` ) x ( `FACT2` x `Lab2` )

May also be used to scale results for a single labeled result item. If absolute values are requested ( [[sabs|SABS]],1), the absolute values of `Lab1` and `Lab2` are used.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SMULT.html
