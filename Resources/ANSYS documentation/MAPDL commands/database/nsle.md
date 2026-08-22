---
apdl: "NSLE"
method: nsle
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.nsle
generated: 2026-08-22
tags: [mapdl-command]
---

# NSLE

PyMAPDL: `mapdl.nsle(type_='', nodetype='', num='', **kwargs)`

Selects those nodes attached to the selected elements.

## Parameters

**type_**

Label identifying the type of node select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

**nodetype**

Label identifying type of nodes to consider when selecting:

- `ALL` - Select all nodes of the selected elements (default).
- `ACTIVE` - Select only the active nodes. An active node is a node that contributes DOFs to the model.
- `INACTIVE` - Select only inactive nodes (such as orientation or radiation).
- `CORNER` - Select only corner nodes.
- `MID` - Select only midside nodes.
- `POS` - Select nodes in position Num.
- `FACE` - Select nodes on face Num.

**num**: Position or face number for NodeType = POS or FACE.

## Notes

**NSLE** selects `NodeType` nodes attached to the currently-selected set of elements. Only nodes on elements in the currently-selected element set can be selected.

When using degenerate hexahedral elements, **NSLE**, `U`, `CORNER` and **NSLE**, `S`, `MID` will not select the same set of nodes because some nodes appear as both corner and midside nodes.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSLE.html
