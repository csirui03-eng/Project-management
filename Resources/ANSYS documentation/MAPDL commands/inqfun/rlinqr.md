---
apdl: "RLINQR"
method: rlinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.rlinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# RLINQR

PyMAPDL: `mapdl.rlinqr(nreal, key, pname='__tmpvar__', **kwargs)`

Get information about a real constant set.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**nreal**: Real constant table number should be 0 for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, and `DB_MAXRECLENG`.

**key**

Information flag.

- 5 - return number of values stored for `nreal`. Return the REAL set width (number of fields)
- `DB_SELECTED` - return select status
  - 0 - real constant table is undefined.
  - -1 - real constant table is unselected.
  - 1 - real constant table is selected
- `DB_NUMDEFINED` - return number of defined real constant tables
- `DB_NUMSELECTED` - return number of selected real constant tables
- `DB_MAXDEFINED` - return highest real constant table defined
- `DB_MAXRECLENG` - return maximum record length (dp words)

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `rlinqr` is based on setting of key.
