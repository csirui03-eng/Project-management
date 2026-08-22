---
apdl: "HPTCREATE"
method: hptcreate
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.hard_points.HardPoints.hptcreate
generated: 2026-08-22
tags: [mapdl-command]
---

# HPTCREATE

PyMAPDL: `mapdl.hptcreate(type_='', entity='', nhp='', label='', val1='', val2='', val3='', **kwargs)`

Defines a hard point.

## Parameters

**type_**

Type of entity on which the hard point will be created.

- `LINE` - Hard point will be created on a line.
- `AREA` - Hard point will be created within an area (not on the boundaries).

**entity**: Number of the line or area on which the hard point will be created.

**nhp**: Number assigned to the hard point. Defaults to the lowest available hard point number.

**label**: If `LABEL` = COORD, `VAL1`, `VAL2`, and `VAL3` are the respective global X, Y, and Z coordinates. If `LABEL` = RATIO, `VAL` 1 is the parameter value (this is available only for lines). Valid parameter values are between 0 and 1. `VAL2` and `VAL3` are ignored.

**val1**: If `LABEL` = RATIO, ratio value for line. If `LABEL` = COORD, global X coordinate value.

**val2**: If `LABEL` = COORD, global Y coordinate value.

**val3**: If `LABEL` = COORD, global Z coordinate value.

## Notes

The ability to enter a parameter value provides a simple way of positioning hard points on lines. For example, to place a hard point halfway along a line, one can simply specify a `VAL1` value of 0.5.

For models imported through the DEFAULT IGES filter, you can place hard points on models only by specifying coordinates (you can't place a hard point using interactive picking).

If you issue any commands that update the geometry of an entity, such as Boolean or simplification commands, any hard points associated with that entity are deleted. Therefore, you should add any hard points after completing the solid model. If you delete an entity that has associated hard points, those hard points are either

- Deleted along with the entity (if the hard point is not associated with any other entities).
- Detached from the deleted entity (if the hard point is associated with additional entities).

When archiving your model ( [[cdwrite|CDWRITE]] ), hardpoint information cannot be written to the IGES file. The `Jobname.cdb` file can be written with the [[cdwrite|CDWRITE]],DB option.

Hard points are only applicable for area and volume meshing, not for beams.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HPTCREATE.html
