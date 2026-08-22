---
apdl: "CLOAD"
method: cload
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cload
generated: 2026-08-22
tags: [mapdl-command]
---

# CLOAD

PyMAPDL: `mapdl.cload(option='', input1='', **kwargs)`

Initiates a [cyclic-loading analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycloadprocess.html#).

**Command default:**

Cyclic load analysis is disabled.

## Parameters

**option**

Option to be applied:

- `DEFINE` - Mark tabular array as a cyclic load table.
- `CYCNUM` - Total number of cycles.
- `CYCTIME` - Cycle time.
- `TSTEP` - Enable time-point-range time-stepping.
- `OUTR` - Select time points for output.

**input1**: Additional input according to the specified Option : This command contains some tables and extra information which can be inspected in the original documentation pointed above.

## Notes

For more information, see [Cyclic-Loading Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advcycloadprocess.html#)

This command is also valid in PREP7 ( [[prep7|/PREP7]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLOAD.html
