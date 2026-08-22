---
apdl: "TOFFST"
method: toffst
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.toffst
generated: 2026-08-22
tags: [mapdl-command]
---

# TOFFST

PyMAPDL: `mapdl.toffst(value='', **kwargs)`

Specifies the temperature offset from absolute zero to zero.

## Parameters

**value**: Degrees between absolute zero and zero of temperature system used (should be positive).

## Notes

Specifies the difference (in degrees) between absolute zero and the zero of the temperature system used. Absolute temperature values are required in evaluating certain expressions, such as for creep, swelling, radiation heat transfer, `MASS71`, etc. (The offset temperature is not used in evaluating emissivity.) Examples are 460° for the Fahrenheit system and 273° for the Celsius system. The offset temperature is internally included in the element calculations and does not affect the temperature input or output. If used in SOLUTION, this command is valid only within the first load step.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TOFFST.html
