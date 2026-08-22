---
apdl: "SFCALC"
method: sfcalc
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.sfcalc
generated: 2026-08-22
tags: [mapdl-command]
---

# SFCALC

PyMAPDL: `mapdl.sfcalc(labr='', labs='', labt='', type_='', **kwargs)`

Calculates the safety factor or margin of safety.

## Parameters

**labr**: Label assigned to results. If same as existing label, the existing values will be overwritten by these results.

**labs**: Labeled result item corresponding to the element stress.

**labt**: Labeled result item corresponding to the element temperature.

**type_**

Type of calculation:

- `0 or 1` - Use safety factor (SF) calculation.
- `2` - Use margin of safety (MS) calculation.
- `3` - Use 1/SF calculation.

## Notes

Calculates safety factor (SF) or margin of safety (MS) as described for the [[sfact|SFACT]] command for any labeled result item (see [[etable|ETABLE]] command) for the selected elements. Use the [[pretab|PRETAB]] or [[pletab|PLETAB]] command to display results. Allowable element stress is determined from the SALLOW- TALLOW table ( [[sallow|SALLOW]], [[tallow|TALLOW]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFCALC.html
