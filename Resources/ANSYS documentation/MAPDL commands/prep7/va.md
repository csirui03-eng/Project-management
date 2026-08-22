---
apdl: "VA"
method: va
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.va
generated: 2026-08-22
tags: [mapdl-command]
---

# VA

PyMAPDL: `mapdl.va(a1='', a2='', a3='', a4='', a5='', a6='', a7='', a8='', a9='', a10='', **kwargs)`

Generates a volume bounded by existing areas.

## Parameters

**a1**, **a2**, **a3**, **a4**, **a5**, **a6**, **a7**, **a8**, **a9**, **a10**: List of areas defining volume. The minimum number of areas is 4. If `A1` = ALL, use all selected ( [[asel|ASEL]] ) areas and ignore `A2` to `A10`. If `A1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `A1`.

## Returns

`int`: Volume number of the volume.

## Notes

This command conveniently allows generating volumes from regions having more than eight keypoints (which is not allowed with the [[v|V]] command). Areas may be input in any order. The exterior surface of a **VA** volume must be continuous, but holes may pass completely through it.

## Examples

Create a simple tetrahedral bounded by 4 areas.

``` python
>>> k0 = mapdl.k('', -1, 0, 0)
>>> k1 = mapdl.k('', 1, 0,  0)
>>> k2 = mapdl.k('', 1, 1, 0)
>>> k3 = mapdl.k('', 1, 0.5, 1)
>>> a0 = mapdl.a(k0, k1, k2)
>>> a1 = mapdl.a(k0, k1, k3)
>>> a2 = mapdl.a(k1, k2, k3)
>>> a3 = mapdl.a(k0, k2, k3)
>>> vnum = mapdl.va(a0, a1, a2, a3)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VA.html
