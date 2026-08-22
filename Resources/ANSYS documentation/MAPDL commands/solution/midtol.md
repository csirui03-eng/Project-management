---
apdl: "MIDTOL"
method: midtol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.midtol
generated: 2026-08-22
tags: [mapdl-command]
---

# MIDTOL

PyMAPDL: `mapdl.midtol(key='', tolerb='', resfq='', **kwargs)`

Sets midstep residual criterion values for structural transient analyses.

**Command default:** For transient structural analysis, the out-of-balance residual is not checked at the midstep.

## Parameters

**key**

Midstep residual criterion activation key.

- `ON or 1` - Activate midstep residual criterion in a structural transient analysis (default).
- `OFF or 0` - Deactivate midstep residual criterion in a structural transient analysis.
- `STAT` - List the current midstep residual criterion setting.

**tolerb**

Midstep residual tolerance or reference value for bisection. Defaults to 100 times the `TOLER` setting of the [[cnvtol|CNVTOL]] command.

If `TOLERB` \> 0, it is used as a tolerance about the typical force and/or moment to compare midstep residual force and/or moment for convergence.

If `TOLERB` \< 0, it is used as a reference force value against which the midstep residual force is compared for convergence. The reference force value is used to compute a reference moment value for midstep residual moment comparison.

If midstep residual force and/or moment has not converged and [[autots|AUTOTS]],ON is used, then `TOLERB` is also used to predict time step size for bisection.

**resfq**

Key to use response frequency computation along with midstep residual criterion for automatic time stepping ( [[autots|AUTOTS]],ON).

- `OFF or 0` - Do not calculate response frequency and do not consider it in the automatic time stepping (default).
- `ON or 1` - Calculate response frequency and consider it in the automatic time stepping.

## Notes

When `TOLERB` is input as a tolerance value ( `TOLERB` \> 0), the typical force and/or moment from the regular time step is used in the midstep residual force and/or moment comparison.

In a structural transient analysis, the suggested tolerance range of `TOLERB` ( `TOLERB` \> 0) is as follows:

- `TOLERB` = 1 to 10 times the `TOLER` setting of the [[cnvtol|CNVTOL]] command for high accuracy solution.
- `TOLERB` = 10 to 100 times the `TOLER` setting of the [[cnvtol|CNVTOL]] command for medium accuracy solution.

\* `TOLERB` = more than 100 times the `TOLER` setting of the [[cnvtol|CNVTOL]] command for low  
accuracy solution.

If the structural transient analysis is elastic and linear, and the load is constant or changes slowly, use a smaller value of `TOLERB` to achieve an accurate solution. If the analysis involves large amounts of energy dissipation, such as elastic-plastic material, `TOLERB` can be larger. If the analysis includes contact or rapidly varying loads, a smaller value of `TOLERB` should be used if high frequency response is important; otherwise, a larger value of `TOLERB` may be used to enable faster convergence with larger time step sizes.

For more information on how the midstep criterion is used by the program, see [Midstep Residual for Structural Dynamic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool6.html#eq3ee0a0c7-284e-4f2b-ad70-338834430235) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MIDTOL.html
