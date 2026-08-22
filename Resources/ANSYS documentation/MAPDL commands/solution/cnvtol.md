---
apdl: "CNVTOL"
method: cnvtol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.cnvtol
generated: 2026-08-22
tags: [mapdl-command]
---

# CNVTOL

PyMAPDL: `mapdl.cnvtol(lab='', value='', toler='', norm='', minref='', **kwargs)`

Sets convergence values for nonlinear analyses.

**Command default:**

For static or transient analysis, check the out-of-balance load for any active degree of freedom using the default `VALUE`, `TOLER`, `NORM`, and `MINREF`. Also check the translational displacement convergence in most cases. For harmonic magnetic analysis, check the out-of-balance of the degrees of freedom. The energy criterion convergence check is off by default.

## Parameters

**lab**

Valid convergence labels.

(table not available in the PyMAPDL source, see the Ansys help page)

**value**

Typical reference value for the specified convergence label ( `Lab` ).

`VALUE` defaults to the maximum of a program calculated reference or `MINREF`. For degrees of freedom, the reference is based upon the selected `NORM` and the current total degree-of- freedom value. For forcing quantities, the reference is based upon the selected `NORM` and the applied loads.

If `VALUE` is negative, the convergence criterion based on the specified label is removed, including the default convergence criterion value. The convergence criterion for all other labels remain as they were (either a default value or a previously specified value).

**toler**

Tolerance value used for the specified `Lab` convergence label. Default values are described below.

- If **CNVTOL** is issued with a `Lab` value specified but no `TOLER` value, the default tolerance values are:
- 0.05 (5%) for displacement (U).
- 1.0E-7 for the joint element constraint check (JOINT). This value rarely needs to be changed. A loose tolerance value may lead to inaccurate or incorrect solutions. When `Lab` = JOINT, `VALUE`, `NORM`, and `MINREF` are ignored.
- 1.0E-3 for the volumetric compatibility check (COMP). When `Lab` = COMP, `VALUE`, `NORM`, and `MINREF` are ignored.
- 0.05 for energy error (ENGY).
- For all other `Lab` labels, the default tolerance value is 0.005 (0.5%).
- If **CNVTOL** is not issued, the `TOLER` defaults are as follows:
- 0.005 (0.5%) for force (F) and moment (M)
- 1.0E-4 (0.01%) for volume (DVOL)
- 0.05 (5%) for displacement (U)
- 0.05 (5%) for hydrostatic pressure (HDSP)
- 1.0 for temperature (TEMP) when the iterative QUASI solver is used ( [[thopt|THOPT]],QUASI,,,,,,1)

If you choose to specify a `TOLER` value, it must be greater than zero and less than 1. This is true for all `Lab` labels.

The program may adjust the force convergence tolerance if you do not explicitly set a value via **CNVTOL**. See [[cnvtol#Notes|Notes for details.]]

**norm**

Specifies norm selection:

- `0` - Infinite norm (check each degree of freedom separately) (default for `Lab` = U and for `Lab` = TEMP when the iterative QUASI solver is used ( [[thopt|THOPT]],QUASI,,,,,,,1).

  The infinite norm is also used for the energy error criterion (ENGY) and is the only option available for ENGY.

- `1` - L1 norm (check absolute value sum).

- `2` - L2 norm (check SRSS value) (default, except for `Lab` = U).

- `3` - Infinite norm (check each degree of freedom separately). The reference is calculated using the infinite norm of the displacement increment of the substep. Valid only for `Lab` = U.

**minref**

The minimum value allowed for the program-calculated reference value. If negative, no minimum is enforced. Used only if `VALUE` is blank. Default values are as follows:

- maximum of 0.01 or internally calculated minimum reference value for force (F), moment (M)
- a small factor times the average element length of the model for displacement (U) convergence
- 0.01 for volume (DVOL) convergence
- 1.0E-4 for gradient field residual (GFRS)
- 1.0E-6 for heat flow (HEAT)
- 1.0E-6 for diffusion flow (RATE)
- 1.0E-12 for charge (CHRG)
- 1.0E-6 for hydrostatic pressure (HDSP)
- 1.0 for temperature (TEMP) when the iterative QUASI solver is used ( [[thopt|THOPT]],QUASI,,,,,,,1)
- 1.0 for energy error convergence (ENGY)
- 0.0 otherwise

## Notes

This command is usually not needed because the default convergence criteria are sufficient for most nonlinear analyses. In rare cases, you may need to use this command to diagnose convergence difficulties.

Values may be set for the degrees of freedom and/or the out-of-balance load for the corresponding forcing quantities.

Issuing **CNVTOL** to set a convergence criterion for a specific convergence label ( `Lab` ) does not affect the convergence criterion for any other label. All other convergence criteria will remain at their default setting or at the value set by a previous **CNVTOL** command.

If **CNVTOL** is not issued for any force convergence label (F, M, DVOL, and so on as listed under the `Lab` argument), the default convergence tolerance for a particular force label is increased dynamically during the Newton-Raphson iterations in the range of 1 to 1.66 times the default value. For example, the F label default tolerance is 0.005. Therefore, the maximum convergence tolerance with the adjustment is 0.0083. This adjustment is not activated until the 8th or higher Newton-Raphson iteration. If you do not want the program to adjust the tolerance, issue **CNVTOL** to specify the convergence tolerance for the appropriate force label.

When using the Mechanical APDL graphical user interface (GUI), if a "Delete" operation in a Nonlinear Convergence Criteria dialog box writes this command to a log file ( `Jobname.LOG` or `Jobname.LGW` ), you will observe that `Lab` is blank, `VALUE` = -1, and `TOLER` is an integer number. In this case, the GUI has assigned a value of `TOLER` that corresponds to the location of a chosen convergence label in the dialog box's list. It is not intended that you type in such a location value for `TOLER` in an interactive session. However, a file that contains a GUI- generated **CNVTOL** command of this form can be used for batch input or with the [[input|/INPUT]] command.

Convergence norms specified with **CNVTOL** may be graphically tracked while the solution is in process using the Graphical Solution Tracking (GST) feature. Issue [[gst|/GST]] to enable or disable GST. By default, GST is ON for interactive sessions and OFF for batch runs.

The energy convergence check (ENGY) is not available when the arc-length method ( [[arclen|ARCLEN]],ON) is used.

For more information on convergence calculations in a nonlinear analysis, see [Convergence](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool10.html#eq17e730e1-975b-4fe6-a06d-86bc08aa77ad)

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CNVTOL.html
