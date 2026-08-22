---
apdl: "LSLK"
method: lslk
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.lslk
generated: 2026-08-22
tags: [mapdl-command]
---

# LSLK

PyMAPDL: `mapdl.lslk(type_='', lskey='', **kwargs)`

Selects those lines containing the selected keypoints.

## Parameters

**type_**

Label identifying the type of line select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

**lskey**

Specifies whether all contained line keypoints must be selected ( [[ksel|KSEL]] ):

- `0` - Select line if any of its keypoints are in the selected keypoint set.
- `1` - Select line only if all of its keypoints are in the selected keypoint set.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSLK.html
