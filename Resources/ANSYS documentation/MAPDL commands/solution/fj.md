---
apdl: "FJ"
method: fj
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.fj
generated: 2026-08-22
tags: [mapdl-command]
---

# FJ

PyMAPDL: `mapdl.fj(elem='', label='', value='', **kwargs)`

Specify forces or moments on the components of the relative motion of a joint element.

## Parameters

**elem**: Element number or ALL to specify all joint elements.

**label**

Valid labels:

- `FX` - Force in local x direction.
- `FY` - Force in local y direction.
- `FZ` - Force in local z direction.
- `MX` - Moment about local x axis.
- `MY` - Moment about local y axis.
- `MZ` - Moment about local z axis.

**value**: Value of the label.

## Notes

Valid for `MPC184` (joint options in KEYOPT(1)).

In a mode-superposition harmonic or transient analysis, you must apply the load in the modal portion of the analysis. Mechanical APDL calculates a load vector and writes it to the `MODE` file, which you can apply via the [[lvscale|LVSCALE]] command.

See [[fjdele|FJDELE]] for information on deleting forces and moments.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FJ.html
