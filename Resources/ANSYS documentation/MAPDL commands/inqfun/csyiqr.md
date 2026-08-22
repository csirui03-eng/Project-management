---
apdl: "CSYIQR"
method: csyiqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.csyiqr
generated: 2026-08-22
tags: [mapdl-command]
---

# CSYIQR

PyMAPDL: `mapdl.csyiqr(ncsy, key, pname='__tmpvar__', **kwargs)`

Get information about a coordinate system.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**ncsy**: Coordinate system reference number should be zero for key= `DB_NUMDEFINED` or `DB_MAXDEFINED`

**key**

Information flag.

- `DB_SELECTED` - return status:
  - 0 - coordinate system is not defined
  - -1 - coordinate system is not selected
  - 1 - coordinate system is selected
- `DB_NUMDEFINED` - number of defined coordinate systems
- `DB_MAXDEFINED` - maximum coordinate system reference number used.

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `csyiqr` is based on setting of key.
