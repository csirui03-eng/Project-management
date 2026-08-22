---
apdl: "STABILIZE"
method: stabilize
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.stabilize
generated: 2026-08-22
tags: [mapdl-command]
---

# STABILIZE

PyMAPDL: `mapdl.stabilize(key='', method='', value='', substpopt='', forcelimit='', recalcdamp='', **kwargs)`

Activates stabilization for all elements that support nonlinear stabilization.

## Parameters

**key**

Key for controlling nonlinear stabilization:

- `OFF` - Deactivate stabilization (default).
- `CONSTANT` - Activate stabilization. The energy-dissipation ratio or damping factor remains constant during the load step.
- `REDUCE` - Activate stabilization. The energy-dissipation ratio or damping factor is reduced linearly to zero at the end of the load step from the specified or calculated value.

**method**

The stabilization-control method:

- `ENERGY` - Use the energy-dissipation ratio as the control. This value is the default when `Key` ≠ OFF.
- `DAMPING` - Use the damping factor as the control.

**value**: The energy-dissipation ratio ( `Method` = ENERGY) or damping factor ( `Method` = DAMPING). This value must be greater than 0 when `Method` = ENERGY or `Method` = DAMPING. When `Method` = ENERGY, this value is usually a number between 0 and 1.

**substpopt**

Option for the first substep of the load step:

- `NO` - Stabilization is not activated for the first substep even when it does not converge after the minimal allowed time increment is reached. This value is the default when `Key` ≠ OFF.
- `MINTIME` - Stabilization is activated for the first substep if it still does not converge after the minimal allowed time increment is reached.
- `ANYTIME` - Stabilization is activated for the first substep. Use this option if stabilization was active for the previous load step via `Key` = CONSTANT.

**forcelimit**: The stabilization force limit coefficient, such that 0 \< `FORCELIMIT` \< 1. The default value is 0.2. To omit a stabilization force check, set this value to 0.

**recalcdamp**

Key for controlling damping recalculation:

- 0 - No recalculation of the damping factor (default).
- 1 - Recalculate the damping factor for the energy-based stabilization-control method.

## Notes

Once issued, a **STABILIZE** command remains in effect until you reissue the command.

For the energy dissipation ratio, specify `VALUE` = 1.0e-4 if you have no prior experience with the current model; if convergence problems are still an issue, increase the value gradually. The damping factor is mesh-, material-, and time-step-dependent; an initial reference value from the previous run (such as a run with the energy-dissipation ratio as input) should suggest itself.

Exercise caution when specifying `SubStpOpt` = MINTIME or ANYTIME for the first load step; Ansys, Inc. recommends this option only for experienced users. If stabilization was active for the previous load step via `Key` = CONSTANT and convergence is an issue for the first substep, specify `SubStpOpt` = ANYTIME.

When the L2-norm of the stabilization force (CSRSS value) exceeds the L2-norm of the internal force multiplied by the stabilization force coefficient, the program issues a message displaying both the stabilization force norm and the internal force norm. The `FORCELIMIT` argument enables you to change the default stabilization force coefficient (normally 20 percent).

When using the energy-based stabilization-control method and `RECALCDAMP` = 1, the damping factor is recalculated in the following cases:

- In an analysis [restart](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS3_12.html#bassolumodres).
- In a nonlinear adaptivity analysis in the substep following the remeshing substep.

This command stabilizes the degrees of freedom for [current-technology elements](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/EL2oldnewtable.html#EL2curtechelembenefits) only. Other elements can be included in the FE model, but their degrees of freedom are not stabilized.

For more information about nonlinear stabilization, see [Unstable Structures](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRUNST.html#strnonstabvsarclen) in the [Structural Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_enercalc_app.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_STABILIZE.html
