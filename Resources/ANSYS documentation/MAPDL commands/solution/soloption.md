---
apdl: "SOLOPTION"
method: soloption
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.soloption
generated: 2026-08-22
tags: [mapdl-command]
---

# SOLOPTION

PyMAPDL: `mapdl.soloption(option='', type_='', value='', **kwargs)`

Specifies solution transition options.

## Parameters

**option**

Transition option:

- `STOT` - Use criterion for transitioning from a static solution to a transient dynamic solution.
- `TTOS` - Use criterion for transitioning from a transient dynamic solution to a static solution.

**type_**: Additional input; varies depending on the `Option` value. See table below.

**value**: Additional input; varies depending on the `Option` and `Type` values. See table below.

## Notes

This command triggers an automatic transition from a static solution to a transient solution based on the specified criterion. The command is valid only in the solution processor ( [[slashsolu|/SOLU]] ) and must be defined either before the first [[solve|SOLVE]] command or during a restart analysis.

If **SOLOPTION** is issued with no arguments specified, the static solution will transition to a quasi-static transient solution if the static solution fails to converge (that is, **SOLOPTION**,STOT,CONV,QUASI).

**SOLOPTION** can be used in a restart even if the base analysis did not include the command. Therefore, a problem that failed in the static analysis can be restarted using this command so that it transitions to a transient solution and solves further. Material densities are required for the transient solution, but they must be defined during the static solution since the restart framework does not permit material density to be defined in the restart analysis.

For more information on using **SOLOPTION**, see [Automatic Transition Between Static and Transient Solutions](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/solutran_limitations.html)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SOLO.html
