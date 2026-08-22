---
apdl: "SMIN"
method: smin
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.smin
generated: 2026-08-22
tags: [mapdl-command]
---

# SMIN

PyMAPDL: `mapdl.smin(labr='', lab1='', lab2='', fact1='', fact2='', **kwargs)`

Forms an element table item from the minimum of two other items.

## Parameters

**labr**: Label assigned to results. If same as existing label, the existing values will be overwritten by these results.

**lab1**: First labeled result item in operation.

**lab2**: Second labeled result item in operation (may be blank).

**fact1**: Scale factor applied to `Lab1`. A (blank) or '0' entry defaults to 1.0.

**fact2**: Scale factor applied to `Lab2`. A (blank) or '0' entry defaults to 1.0.

## Notes

Forms a labeled result item (see [[etable|ETABLE]] command) for the selected elements by comparing two existing labeled result items according to the operation:

`LabR` = ( `FACT1` x `Lab1` ) cmn ( `FACT2` x `Lab2` )

where "cmn" means "compare and save minimum." If absolute values are requested ( [[sabs|SABS]],1), the absolute values of `Lab1` and `Lab2` are used.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SMIN.html
