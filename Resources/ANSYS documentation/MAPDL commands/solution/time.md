---
apdl: "TIME"
method: time
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.time
generated: 2026-08-22
tags: [mapdl-command]
---

# TIME

PyMAPDL: `mapdl.time(time='', **kwargs)`

Sets the time for a load step.

## Parameters

**time**: Time at the end of the load step.

## Notes

Associates the boundary conditions at the end of the load step with a particular `TIME` value.

`TIME` must be a positive, nonzero, monotonically increasing quantity that "tracks" the input history. Units of time should be consistent with those used elsewhere (for properties, creep equations, etc.).

Typically, for the first load step `TIME` defaults to 1. However, for the first load step of a mode-superposition transient analysis ( [[antype|ANTYPE]],TRANS and [[trnopt|TRNOPT]],MSUP), the **TIME** command is ignored and a static solution is performed at `TIME` = 0.

For a full transient analyses, the command's default behavior does not apply. You must specify a time for each load step and it must be greater than the time at the end of the prior load step.

`TIME` does not apply to modal ( [[antype|ANTYPE]],MODAL), harmonic ( [[antype|ANTYPE]],HARMIC), or substructure ( [[antype|ANTYPE]],SUBSTR) analyses.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TIME.html
