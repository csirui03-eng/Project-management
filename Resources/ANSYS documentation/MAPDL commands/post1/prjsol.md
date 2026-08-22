---
apdl: "PRJSOL"
method: prjsol
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prjsol
generated: 2026-08-22
tags: [mapdl-command]
---

# PRJSOL

PyMAPDL: `mapdl.prjsol(item='', comp='', **kwargs)`

Prints joint element output.

## Parameters

**item**

Label identifying the item. Some items also require a component label.

- `DISP` - Relative displacements.
- `ROT` - Relative rotations.
- `VEL` - Relative linear velocities.
- `OMG` - Relative angular velocities.
- `ACC` - Relative linear accelerations.
- `DMG` - Relative angular accelerations.
- `SMISC` - Summable miscellaneous quantities.

**comp**: Component of the item (if required). For `Item` = DISP, ROT, VEL, OMG, ACC, and DMG, enter the direction label, X, Y, or Z. For `Item` = SMISC, enter a valid number.

## Notes

Prints element output for the `MPC184` joint element. The joint element quantities printed are the values for the free or unconstrained relative degrees of freedom.

Only **PRJSOL**,SMISC is available in linear, modal, and linear perturbation analyses.

This command is valid in POST1 only.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRJSOL.html
