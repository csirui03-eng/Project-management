---
apdl: "KPINQR"
method: kpinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.kpinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# KPINQR

PyMAPDL: `mapdl.kpinqr(knmi, key, pname='__tmpvar__', **kwargs)`

Get information about a keypoints.

**Secondary Functions:** Set current keypoints pointer to this keypoints.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

## Parameters

**knmi**: Keypoints for inquire. may be 0 for key=11 thru 15.

**key**

Information flag.

- 1 - return select
  - -1 - unselected
  - 0 - undefined
  - 1 - selected
- 2 - return length (data units)
- 3 - return layer number (for cross reference files return number of entities)
- 4 - return address of first data word
- 5 - return length (in record type units)
- 6 - return compressed record number.
- 11 - return void percent (integer)
- 12 - return number of defined
- 13 - return number of selected
- 14 - return highest number defined
- 15 - return maximum record length (data units)
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
- -1, material number
- -2, type
- -3, real number
- -4, node number, if meshed
- -5, pointer to attached point
- -6, esys number
- -7, element number, if meshed
- -8, Hardpoint stuff
- -9, area number associated with hardpoint
- -10, line number associated with hardpoint
- -11, Orientation kp flag
- -12, local integer workspace
- -101, pointer to keypoint data
- -102, pointer to keypoint fluences
- -103, pointer to keypoint moisture content
- -104, pointer to keypoint voltage
- -105, pointer to keypoint current density
- -106, pointer to keypoint heat generations
- -107, pointer to keypoint virtual displacements
- -108, pointer to parameter data
- -109, pointer to keypoint temperatures
- -110, pointer to keypoint displacements
- -111, pointer to keypoint forces
- -112, pointer to line list

**pname**: Name of the variable where the queried value is stored.

****kwargs**: Extra arguments to be passed to `Mapdl.run <ansys.mapdl.core.Mapdl.run>`.

## Returns

`int or str`

For key=1

- 0 = `knmi` is undefined.
- -1 = `knmi` is unselected.
- 1 = `knmi` is selected.

For key not equal to 1 returned data is based on setting of key.
