---
apdl: "EMATWRITE"
method: ematwrite
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.ematwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# EMATWRITE

PyMAPDL: `mapdl.ematwrite(key='', **kwargs)`

Forces the writing of all the element matrices to `Jobname.emat` None.

## Parameters

**key**

Write key:

- `YES` - Forces the writing of the element matrices to `Jobname.emat` None even if not normally done.
- `NO` - Element matrices are written only if required. This value is the default.

## Notes

The **EMATWRITE** command forces Mechanical APDL to write the `Jobname.emat` file.

If used in the solution processor ( [[slashsolu|/SOLU]] ), this command is valid within the first load step only.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMATWRITE.html
