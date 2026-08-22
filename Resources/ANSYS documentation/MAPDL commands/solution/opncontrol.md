---
apdl: "OPNCONTROL"
method: opncontrol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.opncontrol
generated: 2026-08-22
tags: [mapdl-command]
---

# OPNCONTROL

PyMAPDL: `mapdl.opncontrol(lab='', value='', numstep='', **kwargs)`

Sets decision parameter for automatically increasing the time step interval in a pure thermal analysis.

## Parameters

**lab**

- `TEMP` - Degree-of-freedom label used to base a decision for increasing the time step (substep) interval in a nonlinear or transient analysis. The only DOF label currently supported is TEMP.

- `OPENUPFACTOR` - Key to set a multiplier for increasing the time step interval as specified in `VALUE` \> 1.0 (up to 10.0). Valid only when [[autots|AUTOTS]],ON has been issued.

  The multiplier is set by issuing **OPNCONTROL**,OPENUPFACTOR, `VALUE` as follows:

  - For a pure thermal analysis, if `VALUE` \> 1.0, the OPENUPFACTOR is the minimum of 10.0, `VALUE`.

  If the user does not specify the multiplier, the default is 3.0.

  Generally, `VALUE` \> 3.0 is not recommended. Note that in some rare cases this specification can be overwritten by internal heuristics in determining the new time step interval.

**value**

A context sensitive value that depends on `Lab` :

- If `Lab` = TEMP, `VALUE` is used together with `NUMSTEP` in the algorithm for determining if the time step interval can be increased. The time step interval is increased if the maximum absolute value of the incremental solution is less than `VALUE` for the number of contiguous time steps specified by `NUMSTEP` (default `VALUE` = 0.1).
- If `Lab` = OPENUPFACTOR, `VALUE` is a multiplier (= 1.0 - 10.0) that can be specified for a pure thermal analysis as described above.

**numstep**: Valid only when `Lab` = TEMP. A value used together with `VALUE` in the algorithm for determining if the time step interval can be increased. The time step interval is increased if the maximum absolute value of the incremental solution at the specified TEMP label is less than `VALUE` for the number of contiguous time steps specified by `NUMSTEP` (default `NUMSTEP` = 3).

## Notes

This command is available only for nonlinear static or full transient analyses. **OPNCONTROL** enables an increase in the current time step size. It is analogous to the [[cutcontrol|CUTCONTROL]] command, but with the opposite effect. [[cutcontrol|CUTCONTROL]] reduces the step size for analyses experiencing convergence difficulties while **OPNCONTROL** increases the step size to speed up converging analyses.

The increase in the current time step size via **OPNCONTROL** occurs when:

- a trigger mechanism is encountered and
- a multiplier (greater than 1.0) is set.

Different internal heuristics are used to automatically trigger the increase of the time step for different physics. However, for a pure thermal analysis, an additional trigger to increase the step size can be implemented by issuing **OPNCONTROL**,TEMP.

The multiplier is set by issuing **OPNCONTROL**,OPENUPFACTOR, `VALUE` (see details for different analysis types in the OPENUPFACTOR argument description above).

For linear full transient analysis, where the time step interval can be predominantly determined by the estimated modal frequency (number of solution points in a cycle in the dynamic system), the multiplier set via the OPENUPFACTOR argument may show no effect.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OPNCONTROL.html
