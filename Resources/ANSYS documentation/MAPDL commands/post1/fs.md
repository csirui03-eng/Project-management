---
apdl: "FS"
method: fs
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.fs
generated: 2026-08-22
tags: [mapdl-command]
---

# FS

PyMAPDL: `mapdl.fs(node='', nev='', nlod='', stitm='', c1='', c2='', c3='', c4='', c5='', c6='', **kwargs)`

Stores fatigue stress components at a node.

## Parameters

**node**: Node number corresponding to this location. Used only to associate a node with a new location or to find an existing location.

**nev**: Event number to be associated with these stresses (defaults to 1).

**nlod**: Loading number to be associated with these stresses (defaults to 1).

**stitm**

Starting item number for entering stresses (defaults to 1). If 1, data input in field `C1` of this command is entered as the first item in the list; if 7, data input in field `C1` of this command is entered as the seventh item in the list; etc. Items are as follows:

- `1-6` - SX, SY, SZ, SXY, SYZ, SXZ total stress components
- `7` - Temperature
- `8-13` - SX, SY, SZ, SXY, SYZ, SXZ membrane-plus-bending stress components.
- `14` - Time

**c1**, **c2**, **c3**, **c4**, **c5**, **c6**: Stresses assigned to six locations starting with `STITM`. If a value is already in one of these locations, it will be redefined. A blank retains the previous value (except in the `C1` field, which resets the `STITM` item to zero).

## Notes

Stores fatigue stress components at a node as input on this command instead of from the current data in the database. Stresses are stored according to the event number and loading number specified. The location is associated with that previously defined for this node ( [[fl|FL]] ) or else it is automatically defined. May also be used to modify any previously stored stress components. Stresses input with this command should be consistent with the global coordinate system for any [[fsnode|FSNODE]] or [[fssect|FSSECT]] stresses used at the same location.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FS.html
