---
apdl: "CUTCONTROL"
method: cutcontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.cutcontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# CUTCONTROL

PyMAPDL: `mapdl.cutcontrol(lab='', value='', option='', **kwargs)`

Controls time-step cutback during a nonlinear solution.

## Parameters

**lab**

Specifies the criteria for causing a cutback. Valid labels are:

- `ALIMIT` - Set the maximum edge-flux degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `CONCLIMIT` - Set the maximum concentration degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `CRPLIMIT` - Set values for calculating the maximum equivalent creep ratio allowed within a time step. If the calculated maximum creep ratio exceeds the defined creep-ratio limit, the program performs a cutback. For the first substep or the rebalance substeps after remeshing in [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) or [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html), however, the user-defined maximum plastic-strain limit is ignored.

- `CUTBACKFACTOR` - Key to set the cutback factor, a multiplier for reducing the time step interval to the fraction specified in `VALUE`, where 0 \< `VALUE` \< 1 (default is 0.5 if `VALUE` is not specified.) The option to change the cutback factor is valid only when automatic time stepping is on ( [[autots|AUTOTS]],ON), which is the default.

- `DMGLIMIT` - For damage models (such as [generalized damage and anisotropic damage](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_damageall.html#mat_reganisodmgrefs) ), the maximum allowable damage increment in a time step. If the calculated value exceeds `VALUE`, the program performs a cutback (bisection). If `VALUE` is unspecified, the program does not check the allowable damage increment.

- `DPPLMT` - Set the maximum pore-pressure increment allowed within a time step. If the calculated maximum increment exceeds the specified limit, the program performs a cutback. This option has no default and is valid for coupled [structural-pore-fluid-diffusion](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU_porefluiddiffstruct.html#coupfdsanalysis) analysis only.

- `DSPLIMIT` - Set the maximum degree-of-freedom increment allowed within a time step. Considering all degrees of freedom at every node, if the absolute value of the maximum incremental degree-of- freedom solution within in a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>7</sup>.This cutback trigger criterion is the sole member of the DSPLIMIT set.

- `EMFLIMIT` - Set the maximum electromotive force degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `MAGLIMIT` - Set the maximum scalar magnetic potential degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `MDMG` - For regularized [microplane](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#matmicroplanereadlist) damage models, the maximum allowable microplane homogenized damage increment in a time step. If the calculated value exceeds `VALUE`, the program performs a cutback (bisection). If `VALUE` is unspecified, the program does not check the allowable microplane homogenized damage increment.

- `PLSLIMIT` - Maximum equivalent plastic strain allowed within a time-step (substep). If the calculated value exceeds `VALUE`, the program performs a cutback (bisection). Default: `VALUE` = 0.15 (15 percent)

  If **CUTCONTROL** with `Lab` = PLSLIMIT is not issued, the minimum time step specified is reached, and the maximum plastic limit calculated from the solution exceeds 15 percent, the program generates a warning and continues the Newton iterations.

  If **CUTCONTROL** with `Lab` = PLSLIMIT is issued, the minimum time step specified is reached, and the maximum plastic limit calculated exceeds the specified limit, the program generates an error and stops the Newton iterations. For the first substep or the rebalance substeps after remeshing in [nonlinear mesh adaptivity](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/advmnaexample.html) or [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html), however, the user-defined maximum plastic-strain limit is ignored.

- `PRESLIMIT` - Set the maximum pressure degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `ROTLIMIT` - Set the maximum rotation degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>7</sup>. This cutback trigger criterion is part of the physics limit set.

- `TEMPLIMIT` - Set the maximum temperature degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set and is also valid for [coupled structural-pore-fluid-diffusion-thermal analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cou/Hlp_G_COU_porefluiddiffstruct.html#coupfdsanalysis).

- `ULIMIT` - Set the maximum translation degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>7</sup>. This cutback trigger criterion is part of the physics limit set.

- `VOLTLIMIT` - Set the maximum volt degree-of-freedom increment allowed within a time step. If the absolute value of the calculated increment within a time step exceeds `VALUE`, the program performs a cutback. If not specified, default `VALUE` = 1.0 x 10 <sup>25</sup>. This cutback trigger criterion is part of the physics limit set.

- `VSLIMIT` - For [viscoelastic](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#mat_harmvisco) materials, the [maximum equivalent viscous strain increment](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/evis.html#eq92b60ee3-7e22-457b-9543-53f86d16432a) allowed within a time step. If the calculated value exceeds `VALUE` (default = 0.01), the program performs a cutback (bisection). If `VALUE` = 0, the program does not check the equivalent viscous strain increment.

- `Other Valid Labels:` -

- `NOITERPREDICT` - If `VALUE` = 0 (default), the program predicts the number of iterations for nonlinear convergence and performs a cutback earlier than the number of iterations specified ( [[neqit|NEQIT]] ). This is the recommended option.

  If `VALUE` = 1, the solution iterates (if nonconvergent) to [[neqit|NEQIT]] number of iterations before a cutback is invoked. It is sometimes useful for poorly-convergent problems, but rarely needed in general.

  Bisection is also controlled by contact status change, plasticity or creep strain limit, and other factors. If any of these factors occur, bisection still occurs, regardless of the NOITERPREDICT setting.

- `NPOINT` - Number of points in a cycle for a second order dynamic equation, used to control automatic time- stepping. If the number of solution points per cycle is less than `VALUE`, the program performs a cutback in time step size. Default: `VALUE` = 13 (linear analysis) or 5 (nonlinear analysis). A larger number of points yields a more accurate solution but also increases the solution run time.

  This option works well for linear problems. For nonlinear analyses, other factors such as contact status changes and solution convergence rate can overwrite NPOINT. (See [Automatic Time-Stepping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool6.html#autotime_midstep)

**value**: Numeric value for the specified cutback criterion. For `Lab` = CRPLIMIT only, `VALUE` is the creep criteria for the creep ratio limit.

**option**

Type of creep analysis. Valid for `Lab` = CRPLIMIT only.

- `IMPRATIO` - Set the [maximum creep ratio](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STR8_3.html#STRTimeHCrAjwf0706991137) value for implicit creep. Default = 0.0 (no creep limit control). Any positive value is valid.
- `STSLIMIT` - Stress threshold for calculating the creep ratio. For integration points with effective stress below this threshold, the creep ratio does not cause cutback. Default = 0.0. Any positive value is valid.
- `STNLIMIT` - Elastic strain threshold for calculating the creep ratio. For integration points with effective elastic strain below this threshold, the creep ratio does not cause cutback. Default = 0.0. Any positive value is valid.

## Notes

A cutback is a method for automatically reducing the step size when either the solution error is too large or the solution encounters convergence difficulties during a nonlinear analysis.

If a convergence failure occurs, the program reduces the time step interval to a fraction of its previous size and automatically continues the solution from the last successfully converged time step. If the reduced time step again fails to converge, the program again reduces the time step size and proceeds with the solution. This process continues until convergence is achieved or the minimum specified time step value is reached.

A cutback occurs when a trigger criteria is encountered. The magnitude of the time-step reduction is determined by the cutback factor. Both the trigger and the cutback factor can be specified via **CUTCONTROL** :

- The trigger criteria can be specified for individual physics as detailed in `Lab` descriptions above.
- The cutback factor is 0.5 by default, and can be specified via the CUTBACKFACTOR label described above.

**CUTCONTROL** can be issued multiple times.

### DSPLIMIT Set

DSPLIMIT is the sole label in the DSPLIMIT Set. It can be used to specify the cutback trigger criterion as a limit on the maximum degree-of-freedom increment within a time step, considering all degrees of freedom in an analysis (see DSPLIMIT label description above).

### Physics Limit Set

The physics limit set comprises the following labels: ULIMIT, ROTLIMIT, TEMPLIMIT, PRESLIMIT, VOLTLIMIT, EMFLIMIT, MAGLIMIT, ALIMIT, CONCLIMIT. They can be used to specify distinct degree-of- freedom limits as cutback triggers for individual physics in a multiphysics analysis. Whenever one of these distinct limits is encountered, a cutback is triggered.

Degree-of-freedom limits as cutback trigger criteria are specified via **CUTCONTROL** with labels from either the DSPLIMIT set or the physics limit set. If multiple **CUTCONTROL** commands include labels from both of these sets, the last command issued determines whether the cutback trigger criteria is set by the DSPLIMIT or the physics limit set (see example command listing snippets below).

****Command Default: If no :ref:\`cutcontrol\` commands are issued with labels from the DSPLIMIT set or the physics limit set, the default cutback trigger criterion is DSPLIMIT with VALUE = 1.0 x 10 :sup:\`7\` .****

### Creep and Viscoelastic Analyses

For creep and viscoelastic analyses, the cutback procedure is similar; the process continues until the minimum specified time step size is reached. However, if the criterion is exceeded, the program issues a warning but continues the substep until the analysis is complete. In this case, convergence is achieved but the criterion is not satisfied.

**CUTCONTROL** enables a step size reduction for analyses experiencing convergence difficulties; [[opncontrol|OPNCONTROL]] is an analogous but opposite command that increases the step size to speed up converging analyses.

**Example Usage**

- [Friction Stir Welding Simulation (specify PLSLIMIT on CUTCONTROL)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_tec/tecfricstiranalysis.html#) CUTCONTROL )
- Wire Crimping Simulation (specify PLSLIMIT on **CUTCONTROL** )
- Control the maximum incremental pore pressure allowed in a time step via DPPLIMIT on **CUTCONTROL**
- [Regularized Microplane Damage Models (specify MDMG on CUTCONTROL)](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/microplane.html#) CUTCONTROL )

### Multiple **CUTCONTROL** Commands with labels from both the DSPLIMIT and the Physics Limit Sets

When multiple **CUTCONTROL** commands include labels from both the DSPLIMIT and the physics limit sets, DSPLIMIT is ignored unless `Lab` = DSPLIMIT on the last **CUTCONTROL** command issued as illustrated in the examples below.

- **Label** **on the last** **CUTCONTROL** command issued is from the physics limit set : The cutback trigger criteria are those specified by the physics limit set, and the earlier **CUTCONTROL**,DSPLIMIT command is ignored.

``` apdl
CUTCONTROL,TEMPLIMIT,10     CUTCONTROL,DSPLIMIT,0.7    CUTCONTROL,ULIMIT,0.2   !trigger criteria
is specified by physics limit set (and DSPLIMIT is ignored)    !both ULIMIT and TEMPLIMIT
contribute to the physics limit set of cutback trigger criteria
```

- **Lab= DSPLIMIT on the last** **CUTCONTROL** command issued : DSPLIMIT sets the cutback trigger criterion and earlier **CUTCONTROL** command(s) issued with `Lab` = labels from the physics limit set are ignored.

``` apdl
CUTCONTROL,TEMPLIMIT,10    CUTCONTROL,ULIMIT,0.2     CUTCONTROL,DSPLIMIT,0.7 !trigger criteria is
specified by DSPLIMIT (and physics limit set labels are ignored)
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CUTCONTROL.html
