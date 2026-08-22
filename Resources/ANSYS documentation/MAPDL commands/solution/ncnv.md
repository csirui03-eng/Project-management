---
apdl: "NCNV"
method: ncnv
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.ncnv
generated: 2026-08-22
tags: [mapdl-command]
---

# NCNV

PyMAPDL: `mapdl.ncnv(kstop='', dlim='', itlim='', etlim='', cplim='', **kwargs)`

Sets the key to terminate an analysis.

## Parameters

**kstop**

Program behavior upon nonconvergence:

- `0` - Do not terminate the analysis if the solution fails to converge.
- `1` - Terminate the analysis and the program execution if the solution fails to converge (default).
- `2` - Terminate the analysis, but not the program execution, if the solution fails to converge.

**dlim**: Terminates program execution if the largest nodal DOF solution value (displacement, temperature, etc.) exceeds this limit. Defaults to 1.0E6 for all DOF except MAG and A. Defaults to 1.0E10 for MAG and A.

**itlim**: Terminates program execution if the cumulative iteration number exceeds this limit (defaults to infinity).

**etlim**: Terminates program execution if the elapsed time (seconds) exceeds this limit (defaults to infinity).

**cplim**: Terminates program execution if the CPU time (seconds) exceeds this limit (defaults to infinity).

## Notes

Sets the key to terminate an analysis if not converged, or if any of the following limits are exceeded for nonlinear and full transient analyses: DOF (displacement), cumulative iteration, elapsed time, or CPU time limit. Applies only to static and transient analyses ( [[antype|ANTYPE]] ,STATIC and [[antype|ANTYPE]],TRANS). Time limit checks are made at the end of each equilibrium iteration.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NCNV.html
