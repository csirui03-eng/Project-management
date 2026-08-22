---
apdl: "CPINQR"
method: cpinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.cpinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# CPINQR

PyMAPDL: `mapdl.cpinqr(ncp, key, pname='__tmpvar__', **kwargs)`

Get information about a coupled set.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**ncp**: Coupled set number.

**key**

Inquiry key. It should be zero for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, and `DB_MAXRECLENG`

- `DB_SELECTED` - return select status
  - 1 - coupled set is selected
  - 0 - coupled set in undefined
  - -1 - coupled set in unselected
- `DB_NUMDEFINED` - return number of defined coupled sets
- `DB_NUMSELECTED` - return number of selected coupled sets
- `DB_MAXDEFINED` - return the number of the highest numbered coupled set
- `DB_MAXRECLENG` - return length of largest coupled set record (max record length)
- 2 - return length (data units)
- 3 - return layer number
- 4 - return address of first data word
- 5 - return number of values stored for ncp
- 11 - return void percent (integer)
- 16 - return location of next record
- -1 - return master node for this eqn (this is currently only used by solution DB object)

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `cpinqr` is based on setting of key.
