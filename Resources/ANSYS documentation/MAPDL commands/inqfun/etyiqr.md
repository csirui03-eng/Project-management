---
apdl: "ETYIQR"
method: etyiqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.etyiqr
generated: 2026-08-22
tags: [mapdl-command]
---

# ETYIQR

PyMAPDL: `mapdl.etyiqr(itype, key, pname='__tmpvar__', **kwargs)`

Get information about an element type.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**itype**: Element type number. It should be 0 for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, and `DB_MAXRECLENG`

**key**

Information flag.

- `DB_SELECTED` - return select status:

  - 0 - element type is undefined.
  - -1 - element type is unselected.
  - 1 - element type is selected.

- `DB_NUMDEFINED` - return number of defined element types

- `DB_NUMSELECTED` - return number of selected element types

- `DB_MAXDEFINED` - return highest element type number defined

- `DB_MAXRECLENG` - return maximum record length (int words)

- `-n`- return element characteristic n from `etycom` for element type itype. `n` is correlated to the parameter names in `echprm`. see `elccmt` for definitions of element characteristics.

  > [!NOTE]
  > This will not overwrite the current setting of `etycom`.

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `etyiqr` is based on setting of key.
