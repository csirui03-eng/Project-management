---
apdl: "NUMCMP"
method: numcmp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.numcmp
generated: 2026-08-22
tags: [mapdl-command]
---

# NUMCMP

PyMAPDL: `mapdl.numcmp(label='', **kwargs)`

Compresses the numbering of defined items.

## Parameters

**label**

Items to be compressed:

- `NODE` - Node numbers
- `ELEM` - Element numbers
- `KP` - Keypoint numbers
- `LINE` - Line numbers
- `AREA` - Area numbers
- `VOLU` - Volume numbers
- `MAT` - Material numbers
- `TYPE` - Element type numbers
- `REAL` - Real constant numbers
- `CP` - Coupled set numbers
- `SECN` - Section numbers
- `CE` - Constraint equation numbers
- `CSYS` - Coordinate system numbers
- `ALL` - All item numbers

## Notes

The **NUMCMP** command effectively compresses out unused item numbers by renumbering all the items, beginning with one and continuing throughout the model. The renumbering order follows the initial item numbering order (that is, compression lowers the maximum number by "sliding" numbers down to take advantage of unused or skipped numbers). All defined items are renumbered, regardless of whether or not they are actually used or selected. Applicable related items are also checked for renumbering as described for the merge operation ( [[nummrg|NUMMRG]] ).

Compressing material numbers ( **NUMCMP**,ALL or **NUMCMP**,MAT) does not update the material number referenced by either of the following:

- A temperature-dependent convection or surface-to-surface radiation load ( [[sf|SF]], [[sfe|SFE]], [[sfl|SFL]], [[sfa|SFA]] )
- Real constants for multi-material elements

Compression is usually not required unless memory space is limited and there are large gaps in the numbering sequence.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMCMP.html
