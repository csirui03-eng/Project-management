---
apdl: "SALLOW"
method: sallow
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.sallow
generated: 2026-08-22
tags: [mapdl-command]
---

# SALLOW

PyMAPDL: `mapdl.sallow(strs1='', strs2='', strs3='', strs4='', strs5='', strs6='', **kwargs)`

Defines the allowable stress table for safety factor calculations.

## Parameters

**strs1**, **strs2**, **strs3**, **strs4**, **strs5**, **strs6**: Input up to six allowable stresses corresponding to the temperature points ( [[tallow|TALLOW]] ).

## Notes

Defines the allowable stress table for safety factor calculations ( [[sfact|SFACT]], [[sfcalc|SFCALC]] ). Use the [[stat|STAT]] command to list current allowable stress table. Repeat **SALLOW** to zero table and redefine points (6 maximum).

Safety factor calculations are not supported by PowerGraphics. Both the **SALLOW** and [[tallow|TALLOW]] commands must be used with the Full Model Graphics display method active.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SALLOW.html
