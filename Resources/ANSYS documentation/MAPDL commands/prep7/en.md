---
apdl: "EN"
method: en
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.en
generated: 2026-08-22
tags: [mapdl-command]
---

# EN

PyMAPDL: `mapdl.en(iel='', i='', j='', k='', l='', m='', n='', o='', p='', **kwargs)`

Defines an element by its number and node connectivity.

## Parameters

**iel**: Number assigned to element being defined. If `IEL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**i**: Number of node assigned to first nodal position (node I).

**j**, **k**, **l**, **m**, **n**, **o**, **p**: Number assigned to second (node J) through eighth (node P) nodal position, if any.

## Notes

Defines an element by its nodes and attribute values. Similar to the [[e|E]] command except it allows the element number ( `IEL` ) to be defined explicitly. Element numbers need not be consecutive. Any existing element already having this number will be redefined.

Up to 8 nodes may be specified with the **EN** command. If more nodes are needed for the element, use the [[emore|EMORE]] command. The number of nodes required and the order in which they should be specified are described in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html) for each element type. The current (or default) MAT, TYPE, REAL, SECNUM, and ESYS attribute values are also assigned to the element.

When creating elements with more than 8 nodes using this command and the [[emore|EMORE]] command, it may be necessary to turn off shape checking using the [[shpp|SHPP]] command before issuing this command. If a valid element type can be created without using the additional nodes on the [[emore|EMORE]] command, this command will create that element. The [[emore|EMORE]] command will then modify the element to include the additional nodes. If shape checking is active, it will be performed before the [[emore|EMORE]] command is issued. Therefore, if the shape checking limits are exceeded, element creation may fail before the [[emore|EMORE]] command modifies the element into an acceptable shape.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EN.html
