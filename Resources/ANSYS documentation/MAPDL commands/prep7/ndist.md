---
apdl: "NDIST"
method: ndist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.ndist
generated: 2026-08-22
tags: [mapdl-command]
---

# NDIST

PyMAPDL: `mapdl.ndist(nd1='', nd2='', **kwargs)`

Calculates and lists the distance between two nodes.

## Parameters

**nd1**: First node in distance calculation. If `ND1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nd2**: Second node in distance calculation.

## Returns

`list`: `[DIST, X, Y, Z]` distance between two nodes.

## Notes

**NDIST** lists the distance between nodes `ND1` and `ND2`, as well as the current coordinate system offsets from `ND1` to `ND2`, where the X, Y, and Z locations of `ND1` are subtracted from the X, Y, and Z locations of `ND2` (respectively) to determine the offsets. **NDIST** is valid in any coordinate system except toroidal ( [[csys|CSYS]],3).

**NDIST** returns a variable, called " `_RETURN`," which contains the distance value. You can use this value for various purposes, such as the calculation of distributed loads. In interactive mode, you can access this command by using the Model Query Picker ( Utility Menu\> List\> Picked Entities ), where you can also access automatic annotation functions and display the value on your model.

This command is valid in any processor.

## Examples

Compute the distance between two nodes.

``` python
>>> node1 = (0, 8, -3)
>>> node2 = (13, 5, 7)
>>> node_num1 = mapdl.n("", *node1)
>>> node_num2 = mapdl.n("", *node2)
>>> node_dist = mapdl.ndist(node_num1, node_num2)
>>> node_dist
[16.673332000533065, 13.0, -3.0, 10.0]
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NDIST.html
