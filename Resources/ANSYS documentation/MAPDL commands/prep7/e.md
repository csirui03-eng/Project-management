---
apdl: "E"
method: e
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.e
generated: 2026-08-22
tags: [mapdl-command]
---

# E

PyMAPDL: `mapdl.e(i='', j='', k='', l='', m='', n='', o='', p='', **kwargs)`

Defines an element by node connectivity.

## Parameters

**i**: Number of node assigned to first nodal position (node I). If `I` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**j**, **k**, **l**, **m**, **n**, **o**, **p**: Number assigned to second (node J) through eighth (node P) nodal position, if any.

## Notes

Defines an element by its nodes and attribute values. You can specify up to eight nodes. You can add more nodes if needed ( [[emore|EMORE]] ).

The number of nodes required and the order in which they are specified are described in [Element Input](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_CH2_1.html#aWe8sq3b3ldm) [[numstr|NUMSTR]] ) as generated. The current (or default) MAT, TYPE, REAL, SECNUM and ESYS attribute values are also assigned to the element.

When creating elements with more than eight nodes ( **E** followed by [[emore|EMORE]] ), it may be necessary disable shape-checking ( [[shpp|SHPP]] ) before issuing this command.

If a valid element type can be created without using additional nodes ( [[emore|EMORE]] ), this command creates that element. [[emore|EMORE]] then modifies the element to include the additional nodes. If shape-checking is active, it occurs before [[emore|EMORE]] is issued. If the shape-checking limits are exceeded, therefore, element creation may fail before [[emore|EMORE]] modifies the element into an acceptable shape.

## Examples

Create a single SURF154 element.

``` python
>>> mapdl.prep7()
>>> mapdl.et(1, 'SURF154')
>>> mapdl.n(1, 0, 0, 0)
>>> mapdl.n(2, 1, 0, 0)
>>> mapdl.n(3, 1, 1, 0)
>>> mapdl.n(4, 0, 1, 0)
>>> mapdl.e(1, 2, 3, 4)
1
```

Create a single hexahedral SOLID185 element

``` python
>>> mapdl.et(2, 'SOLID185')
>>> mapdl.type(2)
>>> mapdl.n(5, 0, 0, 0)
>>> mapdl.n(6, 1, 0, 0)
>>> mapdl.n(7, 1, 1, 0)
>>> mapdl.n(8, 0, 1, 0)
>>> mapdl.n(9, 0, 0, 1)
>>> mapdl.n(10, 1, 0, 1)
>>> mapdl.n(11, 1, 1, 1)
>>> mapdl.n(12, 0, 1, 1)
>>> mapdl.e(5, 6, 7, 8, 9, 10, 11, 12)
2
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_E.html
