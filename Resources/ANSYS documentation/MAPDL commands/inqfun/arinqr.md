---
apdl: "ARINQR"
method: arinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.arinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# ARINQR

PyMAPDL: `mapdl.arinqr(anmi, key, pname='__tmpvar__', **kwargs)`

Get information about a area.

**Secondary Functions:** Set current area pointer to this area.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**anmi**: Area for inquire. may be 0 for key=11 thru 15.

**key**

Key as to information needed about the `anmi`.

- 1, return select
- 2, return length (data units)
- 3,
- 11, return void percent (integer)
- 12, return number of defined
- 13, return number of selected
- 14, return highest number defined
- 15, return maximum record length (data units)
- 16, return next record (this increments the next record count)
- -1, material
- -2, type.
- -3, real.
- -4, number of nodes.
- -5,
- -6, number of elements.
- -7, pointer to area in foreign db
- -8, element shape.
- -9, mid-node element key.
- -10, element coordinate system.
- -11, area constraint information.
- 0 - no constraint on this area.
- 1 - symmetry constraint.
- 2 - anti-symmetry
- 3 - both symmetry and anti-symmetry
- -12, local integer workspace
- -13,
- -14,
- -15, section
- -16, color and translucency packed.
- -101, pointer to area data
- -102,
- -103,
- -104,
- -105, pointer to node list.
- -106, pointer to parameter data
- -107, pointer to element list.
- -108,
- -109,
- -110,
- -111,
- -112, pointer to line loop list
- -113, pointer to volume xref
- -114, pointer to sub-area list
- -115, pointer to area presaraes
- -116, pointer to area convections

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`

For key=1

- 0 = `anmi` is undefined.
- -1 = `anmi` is unselected.
- 1 = `anmi` is selected.

For key not equal to 1, the returned data is based on setting of key.
