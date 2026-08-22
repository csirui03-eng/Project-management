---
apdl: "CEINQR"
method: ceinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.ceinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# CEINQR

PyMAPDL: `mapdl.ceinqr(nce, key, pname='__tmpvar__', **kwargs)`

Get information about a constraint equation set.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**nce**: Constraint equation number

**key**

Inquiry key. It should be zero for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, and `DB_MAXRECLENG`

- `DB_SELECTED` - return select status
  - 1 - equation is selected
  - 0 - equation is undefined
  - -1 - equation is unselected
- `DB_NUMDEFINED` - return number of defined constraint equations.
- `DB_NUMSELECTED` - return number of selected constraint equations.
- `DB_MAXDEFINED` - return number of highest numbered constraint equation defined.
- `DB_MAXRECLENG` - return length of longest constraint equation set (max record length)
- 2 - return length (data units)
- 3 - return layer number
- 4 - address of first data word
- 5 - return number of values stored for nce
- 11 - return void percent (integer)
- 16 - return location of next record
- `CE_NONLINEAR` - return 1 if CE is nonlinear
- `CE_ELEMNUMBER` - return associated element number

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `ceinqr` is based on setting of key.
