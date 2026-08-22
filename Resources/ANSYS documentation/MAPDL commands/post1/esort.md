---
apdl: "ESORT"
method: esort
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.esort
generated: 2026-08-22
tags: [mapdl-command]
---

# ESORT

PyMAPDL: `mapdl.esort(item='', lab='', order='', kabs='', numb='', **kwargs)`

Sorts the element table.

**Command default:**

Use ascending element number order.

## Parameters

**item**

Label identifying the item:

- `ETAB` - (currently the only `Item` available)

**lab**

element table label:

- `Lab` - Any user-defined label from the [[etable|ETABLE]] command (input in the `Lab` field of the [[etable|ETABLE]] command).

**order**

Order of sort operation:

- `0` - Sort into descending order.
- `1` - Sort into ascending order.

**kabs**

Absolute value key:

- `0` - Sort according to real value.
- `1` - Sort according to absolute value.

**numb**: Number of elements (element table rows) to be sorted in ascending or descending order ( `ORDER` ) before sort is stopped (remainder will be in unsorted sequence) (defaults to all elements).

## Notes

The element table rows are sorted based on the column containing the `Lab` values. Use [[eusort|EUSORT]] to restore the original order. If **ESORT** is specified with PowerGraphics on ( [[graphics|/GRAPHICS]],POWER), then the nodal solution results listing ( [[prnsol|PRNSOL]] ) will be the same as with the full graphics mode ( [[graphics|/GRAPHICS]],FULL).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESORT.html
