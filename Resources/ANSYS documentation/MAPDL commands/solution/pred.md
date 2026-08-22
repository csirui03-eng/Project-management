---
apdl: "PRED"
method: pred
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.pred
generated: 2026-08-22
tags: [mapdl-command]
---

# PRED

PyMAPDL: `mapdl.pred(sskey='', lskey='', **kwargs)`

Activates a predictor in a nonlinear analysis.

**Command default:**

The default command behavior is to use prediction ( `Sskey` = AUTO). The AUTO option chooses to either use the linear predictor or to turn the predictor OFF. However, prediction does not occur if one or more of these conditions exist:

- Over prediction occurs due to a large residual force or excessive element distortion.
- You are mapping ( [[mapsolve|MAPSOLVE]] ) variables to a new mesh during [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html). (Prediction does not occur for any [[mapsolve|MAPSOLVE]] substeps, nor for the first substep afterwards.)
- You have steady-state analysis defined ( [[sstate|SSTATE]] ), and contact elements exist in the model.

## Parameters

**sskey**

Substep predictor key:

- `AUTO` - The program uses a predictor but, within certain exceptions, automatically switches prediction off. This behavior is the default; see for details.
- `OFF` - No prediction occurs.
- `LINEAR (or ON)` - Use the linear predictor on all substeps after the first.
- `QUADRATIC` - Use the quadratic predictor on all substeps after the second.

**lskey**

Load step predictor:

- `OFF` - No prediction across load steps occurs. This is the default behavior.
- `ON` - Use a predictor also on the first substep of the load step. ( `Sskey` = ON is required.)

## Notes

Activates a predictor in a nonlinear analysis on the degree-of-freedom solution for the first equilibrium iteration of each substep.

When using the arc-length method ( [[arclen|ARCLEN]], [[arctrm|ARCTRM]] ), you cannot issue the DOF solution predictor command ( **PRED** ), the automatic time stepping command ( [[autots|AUTOTS]] ), or the line search command ( [[lnsrch|LNSRCH]] ). If you activate the arc-length method after you set **PRED**, [[autots|AUTOTS]], or [[lnsrch|LNSRCH]], a warning message appears. If you elect to proceed with the arc-length method, the program disables your DOF predictor, automatic time stepping, and line search settings, and the time step size is controlled by the arc-length method internally.

When using step-applied loads, such as [[tunif|TUNIF]], [[bfunif|BFUNIF]], etc., or other types of non- monotonic loads, the predictor may adversely affect the convergence. If the solution is discontinuous, the predictor may need to be turned off.

When performing a nonlinear analysis involving large rotations, the predictor may require using smaller substeps. If the model has rotational degrees-of-freedom, the quadratic predictor could work more efficiently than the linear predictor.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRED.html
