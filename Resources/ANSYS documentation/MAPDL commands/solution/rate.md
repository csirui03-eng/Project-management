---
apdl: "RATE"
method: rate
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.rate
generated: 2026-08-22
tags: [mapdl-command]
---

# RATE

PyMAPDL: `mapdl.rate(option='', **kwargs)`

Specifies whether the effect of creep strain rate will be used in the solution of a load step.

## Parameters

**option**

Activates implicit creep analysis.

- `0 or OFF` - No implicit creep analysis. This option is the default.
- `1 or ON` - Perform implicit creep analysis.

## Notes

Set `Option` = 1 (or ON) to perform an implicit creep analysis ( [[tb|TB]],CREEP with `TBOPT` (equation omitted) 1). For viscoplasticity/creep analysis, `Option` specifies whether or not to include the creep calculation in the solution of a load step. If `Option` = 1 (or ON), the program performs the creep calculation. Set an appropriate time for solving the load step via a [[time|TIME]], `TIME` command.

**Product Restrictions**

This command works only when modeling implicit creep with either von Mises or Hill potentials.

When modeling implicit creep with von Mises potential, you can use the following elements: `LINK180`, `SHELL181`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `SOLID272`, `SOLID273`, `SOLID285`, `SOLSH190`, `BEAM188`, `BEAM189`, `SHELL208`, `SHELL209`, `REINF264`, `SHELL281`, and `ELBOW290`.

When modeling anisotropic creep ( [[tb|TB]],CREEP with [[tb|TB]],HILL), you can also use the following elements: `LINK180`, `SHELL181`, `PLANE182`, `PLANE183`, `SOLID185`, `SOLID186`, `SOLID187`, `BEAM188`, `BEAM189`, `SOLSH190`, `SHELL208`, `SHELL209`, `REINF264`, `REINF265`, `SOLID272`, `SOLID273`, `SHELL281`, `SOLID285`, `PIPE288`, `PIPE289`, and `ELBOW290`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RATE.html
