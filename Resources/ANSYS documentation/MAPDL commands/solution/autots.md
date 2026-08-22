---
apdl: "AUTOTS"
method: autots
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.autots
generated: 2026-08-22
tags: [mapdl-command]
---

# AUTOTS

PyMAPDL: `mapdl.autots(key='', **kwargs)`

Specifies whether to use automatic time stepping or load stepping.

## Parameters

**key**

Automatic time stepping key:

- `OFF` - Do not use automatic time stepping.
- `ON` - Use automatic time stepping (default).
- `AUTO` - The program determines whether to use automatic time stepping (used by Workbench).

## Notes

Specifies whether to use automatic time stepping (or load stepping) over this load step. If `Key` = ON, both time step prediction and time step bisection will be used.

Bisection does not occur with [[thopt|THOPT]],QUASI since it uses only one equilibrium iteration per substep. To ensure bisection, use the iterative QUASI method ( [[thopt|THOPT]],QUASI,,,,,,1).

You cannot use automatic time stepping ( **AUTOTS** ), line search ( [[lnsrch|LNSRCH]] ), or the DOF solution predictor ( [[pred|PRED]] ) with the arc-length method ( [[arclen|ARCLEN]], [[arctrm|ARCTRM]] ). If you activate the arc-length method after you set **AUTOTS**, [[lnsrch|LNSRCH]], or [[pred|PRED]], a warning message appears. If you choose to proceed with the arc-length method, the program disables your automatic time stepping, line search, and DOF predictor settings, and the time step size is controlled by the arc-length method internally.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AUTOTS.html
