---
apdl: "SOLVE"
method: solve
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.solve
generated: 2026-08-22
tags: [mapdl-command]
---

# SOLVE

PyMAPDL: `mapdl.solve(action='', **kwargs)`

Starts a solution.

## Parameters

**action**

Action to be performed on solve (used only for linear perturbation analyses).

- `ELFORM` - Reform all appropriate element matrices in the first phase of a linear perturbation analysis.

## Notes

Starts the solution of one load step of a solution sequence based on the current analysis type and option settings. Use `Action` = ELFORM only in the first phase of a [linear perturbation analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strlinpertother.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SOLVE.html
