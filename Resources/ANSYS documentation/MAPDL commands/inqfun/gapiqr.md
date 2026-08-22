---
apdl: "GAPIQR"
method: gapiqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.gapiqr
generated: 2026-08-22
tags: [mapdl-command]
---

# GAPIQR

PyMAPDL: `mapdl.gapiqr(ngap, key, pname='__tmpvar__', **kwargs)`

Get information about a dynamic gap set.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**ngap**: gap number for inquire (must be zero for now).

**key**

key as to the information needed

- 1, return select
- 2, return length (data units)
- 3,
- 11, return void percent (integer)
- 12, return number of defined
- 13, return number of selected
- 14, return highest number defined
- 15, return maximum record length (data units)

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: Returned data is based on setting of key.
