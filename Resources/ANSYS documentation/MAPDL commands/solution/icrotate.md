---
apdl: "ICROTATE"
method: icrotate
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.icrotate
generated: 2026-08-22
tags: [mapdl-command]
---

# ICROTATE

PyMAPDL: `mapdl.icrotate(node='', omega='', x1='', y1='', z1='', x2='', y2='', z2='', vx='', vy='', vz='', accel='', **kwargs)`

Specifies initial velocity at nodes as a sum of rotation about an axis and translation.

## Parameters

**node**: Node at which the initial velocity is to be specified. If ALL, apply to all selected nodes ( [[nsel|NSEL]] ). A component name may be input for `NODE`.

**omega**: Scalar rotational velocity about the rotational axis.

**x1**, **y1**, **z1**: Coordinates (in the global Cartesian coordinate system) of the beginning point of the rotational axis vector.

**x2**, **y2**, **z2**: Coordinates (in the global Cartesian coordinate system) of the end point of the rotational axis vector.

**vx**: Initial translational velocity in direction x of the nodal coordinate system.

**vy**: Initial translational velocity in direction y of the nodal coordinate system.

**vz**: Initial translational velocity in direction z of the nodal coordinate system.

**accel**

Key to initialize acceleration due to centrifugal effects:

- `(blank)` - Do not initialize acceleration (default).
- `CENT` - Initialize acceleration due to centrifugal effects along with the initial velocity.

## Notes

The **ICROTATE** command specifies initial velocity for all translational degrees of freedom of the specified nodes. The velocity value is a combination of velocity due to rotation about an axis and translation. The velocity at the node is calculated as:

(equation not available in the PyMAPDL source, see the Ansys help page)

where

- v <sup>N</sup> = velocity of node `N` in the nodal coordinate system
- v <sup>trans</sup> = translational velocity input as \[ `Vx`, `Vy`, `Vz` \]
- ω = scalar angular velocity input as `OMEGA`
- x <sup>1</sup> and x <sup>2</sup> denote the coordinates of points prescribing the beginning \[ `X1`, `Y1`, `Z1` \] and end \[ `X2`, `Y2`, `Z2` \] of the rotation axis
- x <sup>N</sup> denotes the coordinates of node `N`

All coordinates are input in the global Cartesian coordinate system, and the velocity due to rotation is then converted to the nodal coordinate system and added to the prescribed translation.

If `ACCEL` = CENT is specified, acceleration due to centrifugal effects is initialized as well. The acceleration at node a <sup>N</sup> is initialized as:

(equation not available in the PyMAPDL source, see the Ansys help page)

The **ICROTATE** command is valid only for static analysis and full method transient analysis ( [[timint|TIMINT]],ON with [[trnopt|TRNOPT]],FULL). The initial value is specified at the beginning of the first load step; that is, at time = 0.0.

The command calculates the nodal velocities and saves them in the database as if the [[ic|IC]] command had been used to calculate these velocities. Thus, when the `Jobname.CDB` or `Jobname.DB` file is written, the velocities prescribed by the **ICROTATE** command appear as [[ic|IC]] commands. All assumptions, recommendations, and restrictions for the [[ic|IC]] command are also true for the **ICROTATE** command.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ICROTATE.html
