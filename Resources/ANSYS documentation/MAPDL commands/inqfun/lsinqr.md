---
apdl: "LSINQR"
method: lsinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.lsinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# LSINQR

PyMAPDL: `mapdl.lsinqr(line, key, pname='__tmpvar__', **kwargs)`

Get information about a line segment.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**lnmi**: Line segment for inquire. It should be 0 for key=11 thru 15.

**key**

key as to information needed about the `lnmi`.

- 1, return select
- 2, return length (data units)
- 3,
- 11, return void percent (integer)
- 12, return number of defined
- 13, return number of selected
- 14, return highest number defined
- 15, return maximum record length (data units)
- 16, return location of next record (this increments the next record count)
- 17, return next record from offset
- -1, material number
- -2, type
- -3, real number
- -4, number of nodes
- -5, esys number
- -6, number of elements
- -7, pointer to line in foreign db
- -8, \# of elem divs in existing mesh
- -9, keypoint 1
- -10, keypoint 2
- -11, color,translucency packed
- -12, local integer workspace (used in delete with sweeps)
- -13, orientation kpa
- -14, orientation kpb
- -15, section id
- -16, \# of elem divs for next mesh
- -17, 0=hard / 1=soft `NDIV`
- -18, 0=hard / 1=soft `SPACE`
- -101, pointer to line segment data
- -102,
- -103,
- -104,
- -105, pointer to node list
- -106,
- -107, pointer to element list
- -108, pointer to parameter data
- -109,
- -110, pointer to line convections
- -111, pointer to line constraints
- -112,
- -113,
- -114, pointer to area list
- -115, pointer to sub-line list
- -116, pointer to line pressures

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`

For key=1

- 0 = `lnmi` is undefined.
- -1 = `lnmi` is unselected.
- 1 = `lnmi` is selected.

For key not equal to 1 returned data is based on setting of key.
