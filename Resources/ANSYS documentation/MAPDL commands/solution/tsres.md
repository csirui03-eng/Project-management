---
apdl: "TSRES"
method: tsres
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.tsres
generated: 2026-08-22
tags: [mapdl-command]
---

# TSRES

PyMAPDL: `mapdl.tsres(array='', **kwargs)`

Defines an array of key times at which the time-stepping strategy changes.

## Parameters

**array**: Identifies an `N` x1x1 array parameter containing the key times at which the heat transfer time- stepping strategy changes (the time step is reset to the initial time step based on [[deltim|DELTIM]] or [[nsubst|NSUBST]] settings). The array name must be enclosed by % signs (for example, `array`). See [[dim|*DIM]] for more information on array parameters.

## Notes

Time values in the array parameter must be in ascending order and must not exceed the time at the end of the load step as defined on the [[time|TIME]] command. The time increment between time points in the array list must be larger than the initial time step defined on the [[deltim|DELTIM]] or [[nsubst|NSUBST]] command. Time values must also fall between the beginning and ending time values of the load step. For multiple load step problems, you must either change the parameter values to fall between the beginning and ending time values of the load step or reissue the command with a new array parameter. To clear the array parameter specification, issue **TSRES**,ERASE. Results can be output at the requested time points if the array or time values in the array are also specified in the [[outres|OUTRES]] command using `FREQ` =`array`. Use this command to reset the time-stepping strategy within a load step. You may need to reset the time-stepping strategy when using tabular time-varying boundary conditions.

See [Steady-State Thermal Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE2_10.html) of the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html) for more information on applying boundary conditions via tabular input. See [Transient Thermal Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE3_12.html) of the [Thermal Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_the/Hlp_G_THE4.html) for more information on defining the key time array.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TSRES.html
