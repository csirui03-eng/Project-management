---
apdl: "ELMIQR"
method: elmiqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.elmiqr
generated: 2026-08-22
tags: [mapdl-command]
---

# ELMIQR

PyMAPDL: `mapdl.elmiqr(ielem, key, pname='__tmpvar__', **kwargs)`

Get information about an element.

**Secondary Functions:** Set current element pointer to this element.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**ielem**: Element number. It should be zero for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, `DB_MAXRECLENG`, or 199

**key**

information flag.

- DB_SELECTED - return select status: (1)
  - 0 - element is undefined.
  - -1 - element is unselected.
  - 1 - element is selected.
- `DB_NUMDEFINED` - return number of defined elements (12)
- `DB_NUMSELECTED` - return number of selected elements (13)
- `DB_MAXDEFINED` - return maximum element number used (14)
- `DB_MAXRECLENG` - return maximum record length (15)
- 2 - return length (int words)
- 3 - return layer number (for cross reference files return number of entities)
- 4 - return address of first data word
- 5 - return length (in record type units)
- 6 - return compressed record number.
- 11 - return void percent (integer)
- 16 - return location of next record (this increments the next record count)
- 17 - pointer to start of index
- 18 - return type of file.
  - 0 - integer
  - 1 - double precision
  - 2 - real
  - 3 - complex
  - 4 - character\*8
  - 7 - index
- 19 - return virtual type of file.
  - 0 - fixed length (4.4 form)
  - 1 - indexed variable length (layer data)
  - 2 - xref data tables
  - 3 - bitmap data (for 32 data item packed records)
  - 4 - data tables (three dimensional arrays)
- 111 - return the maximum number of nodes stored for any element
- 123 - return the maximum number of DP contact data stored for any element
- -1 - material number ( `= -EL_MAT`)
- -2 - element type ( `= -EL_TYPE`)
- -3 - real constant number ( `= -EL_REAL`)
- -4 - element section ID number ( `= -EL_SECT`)
- -5 - coordinate system number ( `= -EL_CSYS`)
- -101 - pointer to element integers etc.

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of `elmiqr` is based on setting of key.
