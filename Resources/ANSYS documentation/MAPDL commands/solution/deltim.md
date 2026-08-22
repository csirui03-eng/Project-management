---
apdl: "DELTIM"
method: deltim
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.deltim
generated: 2026-08-22
tags: [mapdl-command]
---

# DELTIM

PyMAPDL: `mapdl.deltim(dtime='', dtmin='', dtmax='', carry='', **kwargs)`

Specifies the time step sizes to be used for the current load step.

## Parameters

**dtime**

Time step size for this step. If automatic time stepping is used ( [[autots|AUTOTS]] ), `DTIME` is the starting time substep.

If contact elements ( `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA175`, or `CONTA177` ) are used, defaults to `TIME` or `TIME` /20 (where `TIME` is the time at the end of the load step as set on the [[time|TIME]] command), depending on the physics of the model. If none of these contact elements are used, defaults to `TIME`.

**dtmin**: Minimum time step (if automatic time stepping is used). The program automatically determines the default based on the physics of the model.

**dtmax**: Maximum time step (if automatic time stepping is used). The program automatically determines the default based on the physics of the model.

**carry**

Time step carry over key:

- `OFF` - Use `DTIME` as time step at start of each load step.
- `ON` - Use final time step from previous load step as the starting time step (if automatic time stepping is used).

The program automatically determines the default based on the physics of the model.

## Notes

See [[nsubst|NSUBST]] for an alternative input.

Use consistent values for `DTIME` and `TIME` ( [[time|TIME]] ). For example, using 0.9 for `DTIME` and 1.0 for `TIME` results in one time step because 1.0 ( `TIME` ) is divisible by.9 ( `DTIME` ) at most once. If you intend to load in 10 increments over a time span of 1.0, use 0.1 for `DTIME` and 1.0 for `TIME`.

The program calculates the initial incremental time so that ( `EndingTime` - `StartingTime` )/ `DTIME` is an integer, which may affect the initial incremental time that you specify. For example, if the starting time is 0, the ending time is 1, and the initial incremental time is 0.4, the program rounds to the nearest integer and adjusts the time to 0.33333.

For solution efficiency, specify values for all fields of this command.

Changing the time step size upon restarting an analysis during a load step is not recommended. You should only change the time step size between load steps.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DELTIM.html
