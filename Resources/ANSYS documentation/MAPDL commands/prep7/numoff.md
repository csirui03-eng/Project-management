---
apdl: "NUMOFF"
method: numoff
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.numoff
generated: 2026-08-22
tags: [mapdl-command]
---

# NUMOFF

PyMAPDL: `mapdl.numoff(label='', value='', kref='', **kwargs)`

Adds a number offset to defined items.

## Parameters

**label**

Apply offset number to one of the following sets of items:

- `NODE` - Nodes
- `ELEM` - Elements
- `KP` - Keypoints
- `LINE` - Lines
- `AREA` - Areas
- `VOLU` - Volumes
- `MAT` - Materials
- `TYPE` - Element types
- `REAL` - Real constants
- `CP` - Coupled sets
- `SECN` - Section numbers
- `CE` - Constraint equations
- `CSYS` - Coordinate systems

**value**: Offset number value (cannot be negative)

**kref**

Attribute reference key:

0 - Add number offset to defined items only (default)

1 - Add number offset to all attribute references (includes undefined items)

## Notes

Useful for offsetting current model data to prevent overlap if another model is read in. [[cdwrite|CDWRITE]] automatically writes the appropriate **NUMOFF** commands followed by the model data to `File.CDB`. When the file is read, therefore, any model already existing in the database is offset before the model data on the file is read.

Offsetting material numbers with this command ( **NUMOFF**,MAT) does not update the material number referenced by either of the following:

- A temperature-dependent convection or surface-to-surface radiation load ( [[sf|SF]], [[sfe|SFE]], [[sfl|SFL]], [[sfa|SFA]] )
- Real constants for multi-material elements

A mismatch may therefore exist between the material definitions and the material numbers referenced.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMOFF.html
