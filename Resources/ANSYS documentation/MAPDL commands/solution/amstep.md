---
apdl: "AMSTEP"
method: amstep
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.additive_manufacturing.AdditiveManufacturing.amstep
generated: 2026-08-22
tags: [mapdl-command]
---

# AMSTEP

PyMAPDL: `mapdl.amstep(sequence='', val1='', val2='', val3='', val4='', val5='', val6='', **kwargs)`

Specifies the process-sequence steps in an additive manufacturing analysis.

## Parameters

**sequence**

One of the following sequence options:

- `PREHEAT` - `VAL1` - Preheat temperature of the build plate. Default = [[tunif|TUNIF]].

- `BUILD` - `VAL1` - Unused.

  `VAL2` - Ending-layer number (for performing the simulation from the first layer to the specified layer only). Default = last layer necessary to build the part.

  `VAL3` - Number of time steps taken to apply heating. Default = 2.

  `VAL4` - Number of time steps taken between layer additions. Default = 2.

  `VAL5` - Unused.

  `VAL6` - Bias growth factor for time steps between layer additions. Default = 1.

- `COOLDOWN` - `VAL1` - Ambient (room) temperature (to serve as the target cooldown temperature).

  `VAL2` - Cooldown time. If 0 or unspecified, the program calculates the time based on the volume of the part and the convection coefficient ( [[amenv|AMENV]] and [[ampowder|AMPOWDER]] ).

  `VAL3` - Number of time steps taken to cool down. Default = 20.

- `HEATTREAT` - Perform a heat-treat (stress-relief) step.

- `REMOVE` - `VAL1` - The number of a support to remove. Specify 0 for plate.

  `VAL2` - Directional cutoff step size. Only valid if `VAL1` = 0.

  `VAL3` - Directional cutoff angle specified on the X-Y plane from the +X axis. Only valid if `VAL1` = 0. Default = 0 radians.

- `USER` - Perform a user-defined step.

**val1**, **val2**, **val3**, **val4**, **val5**, **val6**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMSTEP.html) for further information.

## Notes

**AMSTEP** executes a process-sequence step:

- In a thermal analysis, `Sequence` = PREHEAT sets the value of the starting temperature of the build plate. It is ignored in a structural analysis.
- `Sequence` = BUILD executes the layer-by-layer build sequence.
- `Sequence` = COOLDOWN executes the cooldown step and must occur after the BUILD step.
- `Sequence` = HEATTREAT performs a heat-treatment step to stress-relieve the part. Issue [[ambuild|AMBUILD]],RTHFILE to point to the heat-treat thermal-cycle results and specify either a relaxation temperature ( [[ammat|AMMAT]] ) or creep properties ( [[tb|TB]] ).
- In a structural analysis, `Sequence` = REMOVE removes the requested support or build plate. It is ignored in a thermal analysis.
- In a structural analysis, `Sequence` = USER can specify an initial step (such as bolt-pretension the build plate) or a final step (such as a manufacturing postprocessing step).

For `Sequence` = BUILD and `Sequence` = COOLDOWN, the number of time steps specified determines the accuracy of the captured temperature profile. For distortion and global residual stresses, the default is usually sufficient. With some materials (Al alloys in particular), the default of evenly spaced time steps during the build ( `Sequence` = BUILD) may not adequately capture the cooldown. The bias growth factor ( `VAL6` ) adjusts the time spacing to better resolve temperatures as they cool between layers.

For `Sequence` = REMOVE, directional cutoff is activated when `VAL1` is set to 0 (plate), and a value is given for `VAL2` (cut step size). This option will sequentially remove the first layer of elements in a series of steps with each step moving the specified distance ( `VAL2` ). The cutoff steps will continue across the entire part in the direction of the specified angle ( `VAL3` ). If neither `VAL1` nor `VAL2` are specified, the entire base is removed in a single instantaneous step.

When `Sequence` = USER, the process-sequence steps are bypassed, and the usual nonlinear solution is performed during this step. All applicable load and load step options are accessible. If USER is the initial step, all times are offset by the TIME associated with the USER step.

This command starts a solution. You must remain in SOLUTION between sequence steps.

This command is valid in the SOLUTION processor only.

For more information, including a list of the elements and commands used in an additive manufacturing analysis, see [AM Process Simulation in Workbench Additive](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/add_ag/add_ag_AM_in_WB.html#add_ag_load_addon)

**Product Restrictions**

Ansys Mechanical Enterprise PrepPost This command is not valid.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMSTEP.html
