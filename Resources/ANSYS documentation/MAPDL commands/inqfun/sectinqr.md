---
apdl: "SECTINQR"
method: sectinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.sectinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# SECTINQR

PyMAPDL: `mapdl.sectinqr(nsect, key, pname='__tmpvar__', **kwargs)`

Get information about a section id set.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**nsect**: Section id table number should be 0 for key=11, `DB_NUMDEFINED`, `DB_NUMSELECTED`, `DB_MAXDEFINED`, and `DB_MAXRECLENG`.

**key**

Information flag.

- `DB_SELECTED` - return select status
  - 0 - ection id table is undefined.
  - -1 - section id table is unselected.
  - 1 - section id table is selected
- `DB_NUMDEFINED` - return number of defined section id tables
- `DB_NUMSELECTED` - return number of selected section id tables
- `DB_MAXDEFINED` - return highest section id table defined
- `DB_MAXRECLENG` - return maximum record length (dp words)
- 2 - return length (dp words)
- 3 - return layer number (for cross reference files return number of entities)
- 4 - return address of first data word
- 5 - return length (in record type units)
- 6 - return compressed record number.
- 11 - return void percent (integer)
- 16 - return location of next record (this increments the next record count)
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

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`: The returned value of sectinqr is based on setting of key.
