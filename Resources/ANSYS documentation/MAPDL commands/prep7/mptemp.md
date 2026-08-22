---
apdl: "MPTEMP"
method: mptemp
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mptemp
generated: 2026-08-22
tags: [mapdl-command]
---

# MPTEMP

PyMAPDL: `mapdl.mptemp(sloc='', t1='', t2='', t3='', t4='', t5='', t6='', **kwargs)`

Defines a temperature table for material properties.

## Parameters

**sloc**: Starting location in table for entering temperatures. For example, if `SLOC` = 1, data input in the `T1` field applies to the first constant in the table. If `SLOC` = 7, data input in the `T1` field applies to the seventh constant in the table, etc. Defaults to the last location filled + 1.

**t1**, **t2**, **t3**, **t4**, **t5**, **t6**: Temperatures assigned to six locations starting with `SLOC`. If a value is already in this location, it will be redefined. A blank (or zero) value for `T1` resets the previous value in `SLOC` to zero. A value of zero can only be assigned by `T1`. Blank (or zero) values for `T2` to `T6` leave the corresponding previous values unchanged.

## Notes

Defines a temperature table to be associated with the property data table ( [[mpdata|MPDATA]] ). These temperatures are also used for polynomial property evaluation, if defined ( [[mp|MP]] ). Temperatures must be defined in non-descending order. Issue [[mater|MATER]] \$ [[stat|STAT]] to list the current temperature table. Repeat **MPTEMP** command for additional temperatures (100 maximum). If all arguments are blank, the temperature table is erased.

For clear definition, the temperature range you define with the **MPTEMP** command should include the entire range you'll use in subsequently defined materials. To assist the user in this, the first (and only the first) excursion out of the temperature range defined by the **MPTEMP** commands is flagged with a warning message. Similarly, the reference temperature ( [[tref|TREF]] or [[mp|MP]] ,REFT commands) should also fall in this same temperature range. If not and [[mp|MP]],ALPX was used, a note will be output. If not, and [[mp|MP]],CTEX or [[mp|MP]],THSX was used, an error message will be output.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPTEMP.html
