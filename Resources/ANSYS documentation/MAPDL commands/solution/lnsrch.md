---
apdl: "LNSRCH"
method: lnsrch
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.lnsrch
generated: 2026-08-22
tags: [mapdl-command]
---

# LNSRCH

PyMAPDL: `mapdl.lnsrch(key='', lstol='', lstrun='', **kwargs)`

Activates a line search to be used with Newton-Raphson.

## Parameters

**key**

Line search key:

- `OFF` - Do not use a line search.
- `ON` - Use a line search. Note, adaptive descent is suppressed when **LNSRCH** is on unless explicitly requested on the [[nropt|NROPT]] command. Having line search on and adaptive descent on at the same time is not recommended.
- `AUTO` - The program automatically switches line searching ON and OFF between substeps of a load step as needed. This option is recommended.

**lstol**: Line search convergence tolerance (default = 0.5).

**lstrun**: Truncation key for the line search parameter. Default = OFF, meaning no truncation. To activation truncation, input the number of digits to use after the decimal point for the line search parameter. (See [Line Search](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool10.html#eq7ef4bddb-f782-469d-ad98-a2e8f4a9309c)

## Notes

Activates a line search to be used with the Newton-Raphson method ( [[nropt|NROPT]] ). Line search is an alternative to adaptive descent (see [Line Search](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool10.html#eq7ef4bddb-f782-469d-ad98-a2e8f4a9309c)

**LNSRCH**,AUTO can be very efficient for problems in which **LNSRCH** is needed at only certain substeps.

You cannot use line search ( **LNSRCH** ), automatic time stepping ( [[autots|AUTOTS]] ), or the DOF solution predictor ( [[pred|PRED]] ) with the arc-length method ( [[arclen|ARCLEN]], [[arctrm|ARCTRM]] ). If you activate the arc-length method after you set **LNSRCH**, [[autots|AUTOTS]], or [[pred|PRED]], a warning message appears. If you choose to proceed with the arc-length method, the program disables your line search, automatic time stepping, and DOF predictor settings, and the time step size is controlled by the arc-length method internally.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LNSRCH.html
