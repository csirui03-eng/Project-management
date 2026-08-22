---
apdl: "SFACT"
method: sfact
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.sfact
generated: 2026-08-22
tags: [mapdl-command]
---

# SFACT

PyMAPDL: `mapdl.sfact(type_='', **kwargs)`

Allows safety factor or margin of safety calculations to be made.

## Parameters

**type_**

Type of calculation:

- `0` - No nodal safety factor or margin of safety calculations.
- `1` - Calculate and store safety factors in place of nodal stresses.
- `2` - Calculate and store margins of safety in place of nodal stresses.

## Notes

Allows safety factor (SF) or margin of safety (MS) calculations to be made for the average nodal stresses according to:

SF = SALLOW/\|Stress\|

MS = (SALLOW/\|Stress\|) - 1.0

Calculations are done during the display, select, or sort operation in the active coordinate system ( [[rsys|RSYS]] ) with results stored in place of the nodal stresses. Use the [[prnsol|PRNSOL]] or [[plnsol|PLNSOL]] command to display the results.

The results are meaningful only for the stress (SIG1, SIGE, etc.) upon which [[sallow|SALLOW]] is based. Nodal temperatures used are those automatically stored for the node. Related commands are [[sfcalc|SFCALC]], [[sallow|SALLOW]], [[tallow|TALLOW]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFACT.html
