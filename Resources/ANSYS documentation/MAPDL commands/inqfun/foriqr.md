---
apdl: "FORIQR"
method: foriqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.foriqr
generated: 2026-08-22
tags: [mapdl-command]
---

# FORIQR

PyMAPDL: `mapdl.foriqr(node, key, pname='__tmpvar__', **kwargs)`

Get information about nodal loads.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**node**: Number of node being inquired about. should be 0 for key = `DB_MAXDEFINED` or `DB_NUMDEFINED`.

**key**

Key as to information needed

- 1 - return force mask for node
- `DB_MAXDEFINED` - return number of nodal loadings in model.
- `DB_NUMDEFINED` - return number of nodal loadings in model.

> [!NOTE]
> Both `DB_MAXDEFINED` and `DB_NUMDEFINED`, produce the same functionality.

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `foriqr` is based on setting of key.
