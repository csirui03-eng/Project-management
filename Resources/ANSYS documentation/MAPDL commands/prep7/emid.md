---
apdl: "EMID"
method: emid
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.emid
generated: 2026-08-22
tags: [mapdl-command]
---

# EMID

PyMAPDL: `mapdl.emid(key='', edges='', **kwargs)`

Adds or removes midside nodes.

## Parameters

**key**

Add or remove key:

- `ADD` - Add midside node to elements (default).
- `REMOVE` - Remove midside nodes from elements.

**edges**

- `ALL` - Add (or remove) midside nodes to (from) all edges of all selected elements, independent of which nodes are selected (default).
- `EITHER` - Add (or remove) midside nodes only to (from) element edges which have either corner node selected.
- `BOTH` - Add (or remove) midside nodes only to (from) element edges which have both corner nodes selected.

## Notes

This command adds midside nodes to (or removes midside nodes from) the selected elements. For this to occur, the selected elements must be midside node capable, the active element type ( [[type|TYPE]] ) must allow midside node capability, and the relationship between the finite element model and the solid model (if any) must first be disassociated ( [[modmsh|MODMSH]] ).

By default, **EMID** generates a midside node wherever a zero (or missing) midside node occurs for that element. You can control this and add (or remove) midside nodes selectively by using the `Edges` argument. Nodes are located midway between the two appropriate corner nodes based on a linear Cartesian interpolation. Nodal coordinate system rotation angles are also linearly interpolated. Connected elements share the same midside node. Node numbers are generated sequentially from the maximum node number.

The **EMID** command is useful for transforming linear element types to quadratic element types having the same corner node connectivity.

**EMID** is also useful for transforming elements created outside of the program.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMID.html
