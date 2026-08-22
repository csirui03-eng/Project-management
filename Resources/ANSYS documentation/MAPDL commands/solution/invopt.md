---
apdl: "INVOPT"
method: invopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.invopt
generated: 2026-08-22
tags: [mapdl-command]
---

# INVOPT

PyMAPDL: `mapdl.invopt(option='', **kwargs)`

Enables or disables inverse solving for the current load step.

## Parameters

**option**

Enables or disables inverse solving for a load step:

- `ON` - Enable.
- `OFF` - Disable and revert to forward solving (default).

## Notes

`Option` = ON is valid only at the first load step of a static analysis. Large-deflection effects must be enabled ( [[nlgeom|NLGEOM]],ON). The unsymmetric solver ( [[nropt|NROPT]],UNSYM) is required and the program selects it automatically.

After issuing **INVOPT**,ON, inverse solving remains in effect until **INVOPT**,OFF is issued. The solution then reverts to traditional forward solving (default).

This command cannot be issued during a restart. `Option` can only be changed between load steps.

For more information, see [Nonlinear Static Analysis with Inverse Solving](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/strnonlininversesol.html#strinvsolvlimit)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INVOPT.html
