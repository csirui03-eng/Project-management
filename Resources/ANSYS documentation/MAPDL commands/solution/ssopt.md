---
apdl: "SSOPT"
method: ssopt
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.ssopt
generated: 2026-08-22
tags: [mapdl-command]
---

# SSOPT

PyMAPDL: `mapdl.ssopt(option='', par1='', par2='', par3='', par4='', par5='', **kwargs)`

Defines a solution option for soil analysis.

## Parameters

**option**

Solution option to define:

- `GEOSTATIC` - Geostatic equilibrium step for soil analysis.
- `CONSOLIDATION` - Consolidation step for soil analysis.
- `STOP` - Stop condition for soil consolidation analysis.
- `SFSW` - Specific weight load.

**par1**, **par2**, **par3**, **par4**, **par5**: Parameters for the specified `Option`.

## Notes

**Valid ParValues for Each Option** \* `Option = GEOSTATIC` - No parameter values required.

- `Option = CONSOLIDATION` - No parameter values required.

- `Option = STOP` - `Par1` :

  - SSTATE - The steady-state solution threshold of incremental pore pressure in a step.
  - OFF - Deactivate steady-state solution check.

  `Par2` :

  - Valid only when `Par1` = SSTATE.
  - A positive value to define the maximum pore pressure increment in a step, or a negative value to define the percentage of incremental pore pressure in a step to maximum pore pressure in the solution.

- `Option = SFSW` - `Par1, Par2, Par3` :

  - The specific weight load direction. ( Default : The -Y axis in the global coordinate system.)

  `Par4` :

  - OFF - Ignore the specific bulk weight (default).
  - ON - Account for the specific bulk weight load.

  `Par5` :

  - OFF - Ignores the fluid specific weight (default).
  - ON - Account for the fluid specific weight.

The **SSOPT** command defines solution options for soil analysis ( [[antype|ANTYPE]],SOIL) only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SSOPT.html
