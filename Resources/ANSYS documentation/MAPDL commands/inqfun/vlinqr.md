---
apdl: "VLINQR"
method: vlinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.vlinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# VLINQR

PyMAPDL: `mapdl.vlinqr(vnmi, key, pname='__tmpvar__', **kwargs)`

Get information about a volume.

**Secondary Functions:** Set current volume pointer to this volume.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**vnmi**: Volume for inquire. may be 0 for key=11 thru 15.

**key**

Key as to information needed about the `vnmi`.

- 1, return select
- 2, return length (data units)
- 3,
- 11, return void percent (integer)
- 12, return number of defined
- 13, return number of selected
- 14, return highest number defined
- 15, return maximum record length (data units)
- 16, return next record
- -1, material
- -2, type.
- -3, real.
- -4, number of nodes.
- -5, KZ1 - 1st kpt for elem Z
- -6, number of elements.
- -7, pointer to volume in foreign db
- -8, element shape.
- -9, (`section id`)\*10 + 2
- -10, element coordinate system.
- -11, KZ2 - 2nd kpt for elem Z
- -12, color and transparency packed
- -101, pointer volume data file.
- -102,
- -103,
- -104,
- -105, pointer to node list.
- -106, pointer to volume pvolmeter dat
- -107, pointer to element list.
- -108,
- -109,
- -110, pointer to sub-volume list
- -111,
- -112, pointer to area shell list

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`

For key=1

- 0 = `vnmi` is undefined.
- -1 = `vnmi` is unselected.
- 1 = `vnmi` is selected.

For key ne 1 returned data is based on setting of key.
