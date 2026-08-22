---
apdl: "NUMSTR"
method: numstr
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.numstr
generated: 2026-08-22
tags: [mapdl-command]
---

# NUMSTR

PyMAPDL: `mapdl.numstr(label='', value='', **kwargs)`

Establishes starting numbers for automatically numbered items.

## Parameters

**label**

Apply starting number to one of the following sets of items:

- `NODE` - Node numbers. `Value` defaults (and is continually reset) to 1 + maximum node number in model. Cannot be reset lower.
- `ELEM` - Element numbers. `Value` defaults (and is continually reset) to 1 + maximum element number in model. Cannot be reset lower.
- `KP` - Keypoint numbers. `Value` defaults to 1. Only undefined numbers are used. Existing keypoints are not overwritten.
- `LINE` - Line numbers. `Value` defaults to 1. Only undefined numbers are used. Existing lines are not overwritten.
- `AREA` - Area numbers. `Value` defaults to 1. Only undefined numbers are used. Existing areas are not overwritten.
- `VOLU` - Volume numbers. `Value` defaults to 1. Only undefined numbers are used. Existing volumes are not overwritten.
- `DEFA` - Default. Returns all starting numbers to their default values.

**value**: Starting number value.

## Notes

Establishes starting numbers for various items that may have numbers automatically assigned (such as element numbers with the [[egen|EGEN]] command, and node and solid model entity numbers with the mesh like [[amesh|AMESH]], [[vmesh|VMESH]], etc.. Use **NUMSTR**,STAT to display settings. Use **NUMSTR**,DEFA to reset all specifications back to defaults. Defaults may be lowered by deleting and compressing items (that is, [[ndele|NDELE]] and [[numcmp|NUMCMP]],NODE for nodes, etc.).

A mesh clear operation ( [[vclear|VCLEAR]], [[aclear|ACLEAR]], [[lclear|LCLEAR]], and [[kclear|KCLEAR]] ) automatically sets starting node and element numbers to the highest unused numbers. If a specific starting node or element number is desired, issue **NUMSTR** after the clear operation.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMSTR.html
