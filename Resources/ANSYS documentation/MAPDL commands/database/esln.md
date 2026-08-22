---
apdl: "ESLN"
method: esln
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.esln
generated: 2026-08-22
tags: [mapdl-command]
---

# ESLN

PyMAPDL: `mapdl.esln(type_='', ekey='', nodetype='', **kwargs)`

Selects those elements attached to the selected nodes.

## Parameters

**type_**

Label identifying the type of element selected:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

**ekey**

Node set key:

- `0` - Select element if any of its nodes are in the selected nodal set (default).
- `1` - Select element only if all of its nodes are in the selected nodal set.

**nodetype**

Label identifying type of nodes to consider when selecting:

- `ALL` - Select elements considering all of their nodes (default).
- `ACTIVE` - Select elements considering only their active nodes. An active node is a node that contributes DOFs to the model.
- `INACTIVE` - Select elements considering only their inactive nodes (such as orientation or radiation nodes).
- `CORNER` - Select elements considering only their corner nodes.
- `MID` - Select elements considering only their midside nodes.

## Notes

**ESLN** selects elements which have any (or all `EKEY` ) `NodeType` nodes in the currently-selected set of nodes. Only elements having nodes in the currently-selected set can be selected.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESLN.html
