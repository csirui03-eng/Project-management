---
apdl: "BIOT"
method: biot
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.biot
generated: 2026-08-22
tags: [mapdl-command]
---

# BIOT

PyMAPDL: `mapdl.biot(label='', **kwargs)`

Calculates the Biot-Savart source magnetic field intensity.

**Command default:**

Calculate the H<sub>s</sub> field upon encountering the first [[solve|SOLVE]] command to produce a source field.

## Parameters

**label**

Controls the Biot-Savart calculation:

- `NEW` - Calculate the magnetic source field intensity (H<sub>s</sub> ) from the selected set of source elements to the selected set of nodes. Overwrite any existing H<sub>s</sub> field values.
- `SUM` - Calculate the H<sub>s</sub> field from the selected set of source elements to the selected set of nodes. Accumulate with any existing H<sub>s</sub> field values.

## Notes

Calculates the Biot-Savart source magnetic field intensity (H<sub>s</sub> ) at the selected nodes from the selected source elements. The calculation is done at the time the **BIOT** command is issued.

Source elements include primitives described by element `SOURC36`, and coupled-field elements `SOLID5`, `LINK68`, and `SOLID98`. Current conduction elements do not have a solved-for current distribution from which to calculate a source field until after the first substep. Inclusion of a current conduction element H<sub>s</sub> field will require a subsequent **BIOT**,SUM command (with `SOURC36` elements unselected) and a [[solve|SOLVE]] command.

The units of H<sub>s</sub> are as specified by the current [[emunit|EMUNIT]] command setting.

This command is also valid in PREP7.

Distributed-Memory Parallel (DMP) Restriction When used with `SOLID5`, `LINK68`, or `SOLID98`, the **BIOT** command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BIOT.html
