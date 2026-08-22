---
apdl: "KNODE"
method: knode
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.knode
generated: 2026-08-22
tags: [mapdl-command]
---

# KNODE

PyMAPDL: `mapdl.knode(npt='', node='', **kwargs)`

Defines a keypoint at an existing node location.

## Parameters

**npt**: Arbitrary reference number for keypoint. If zero, the lowest available number is assigned ( [[numstr|NUMSTR]] ).

**node**: Node number defining global X, Y, Z keypoint location. If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE`.

## Returns

`int`: Keypoint number of the generated keypoint.

## Examples

Create a keypoint at a node at (1, 2, 3)

``` python
>>> nnum = mapdl.n('', 1, 2, 3)
>>> knum1 = mapdl.knode('', nnum)
>>> knum1
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KNODE.html
