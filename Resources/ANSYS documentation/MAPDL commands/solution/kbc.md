---
apdl: "KBC"
method: kbc
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.kbc
generated: 2026-08-22
tags: [mapdl-command]
---

# KBC

PyMAPDL: `mapdl.kbc(key='', omgsqrdkey='', **kwargs)`

Specifies ramped or stepped loading within a load step.

## Parameters

**key**

Ramping key:

- `0` - Loads are linearly interpolated (ramped) for each substep from the values of the previous load step to the values of this load step. This is the default value.
- `1` - Loads are step changed (stepped) at the first substep of this load step to the values of this load step (that is, the same values are used for all substeps). Useful for rate-dependent behavior (for example, creep, viscoplasticity, etc.) or transient load steps only.

**omgsqrdkey**

Key for the interpolation of the rotational velocity loading (only supported when `KEY` = 0):

- `0` - Rotational velocities are linearly interpolated. This is the default.
- `1` - A quadratic interpolation is used for the rotational velocities ( [[omega|OMEGA]], [[cmomega|CMOMEGA]], and [[cmrotate|CMROTATE]] ). All other loads are interpolated linearly.

## Notes

Specifies whether loads applied to intermediate substeps within the load step are to be stepped or ramped. Used only if `DTIME` on the [[deltim|DELTIM]] command is less than the time span or, conversely, if `NSBSTP` on the [[nsubst|NSUBST]] command is greater than one. Flags (FSI, MXWF, MVDI, etc.) are always stepped.

Changing the ramping `KEY` (that is, switching between ramped and stepped boundary conditions) between load steps is not recommended.

For ramped loading ( **KBC**,0), when a load is applied for the first time, it is interpolated from zero to the value of the current load step, and not from the initial condition or value of the degree of freedom from the previous load step.

Spatially varying tabular loads or boundary conditions do not support direct ramping or stepping options and, instead, apply their full values according to the supplied tabular functions regardless of the **KBC** setting.

Regardless of the **KBC** setting, any tabular load is applied as step change. This is the case, for example, for a static or harmonic cyclic symmetry analysis with a load that varies by sector ( [[cycopt|CYCOPT]], LDSECT). Note that when tabular and non-tabular loads are present in the same analysis, the non-tabular loads are ramped or stepped according to the **KBC** setting.

Irrespective of the **KBC** setting, loads are usually step-removed. See [Stepping or Ramping Loads](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS2_7.html#bas.ch.2.tab.11.ft.5) in the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for more information.

It is sometimes difficult to obtain successful convergence with stepped loading in a nonlinear transient problem. If divergence is encountered, determine if stepped loading was used by default, then determine if it is appropriate for the analysis.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KBC.html
