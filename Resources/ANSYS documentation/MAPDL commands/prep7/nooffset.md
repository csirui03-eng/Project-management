---
apdl: "NOOFFSET"
method: nooffset
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.nooffset
generated: 2026-08-22
tags: [mapdl-command]
---

# NOOFFSET

PyMAPDL: `mapdl.nooffset(label='', **kwargs)`

Prevents the [[cdread|CDREAD]] command from offsetting specified data items

## Parameters

**label**

Specifies items not to be offset.

- `NODE` - Node numbers
- `ELEM` - Element numbers
- `KP` - Keypoint numbers
- `LINE` - Line numbers
- `AREA` - Area numbers
- `VOLU` - Volume numbers
- `MAT` - Material numbers
- `TYPE` - Element type numbers
- `REAL` - Real constant numbers
- `CSYS` - Coordinate system numbers
- `SECN` - Section numbers
- `CP` - Coupled set numbers
- `CE` - Constraint equation numbers
- `CLEAR` - All items will be offset
- `STATUS` - Shows which items are specified not to be offset.

## Notes

The **NOOFFSET** command specifies data items not to be offset by a set of data read from a [[cdread|CDREAD]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NOOFFSET.html
