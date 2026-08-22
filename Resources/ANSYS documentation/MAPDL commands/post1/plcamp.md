---
apdl: "PLCAMP"
method: plcamp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.plcamp
generated: 2026-08-22
tags: [mapdl-command]
---

# PLCAMP

PyMAPDL: `mapdl.plcamp(option='', slope='', unit='', freqb='', cname='', stabval='', keyallfreq='', keynegfreq='', **kwargs)`

Plots Campbell diagram data for applications involving rotating structure dynamics.

## Parameters

**option**

Flag to activate or deactivate sorting of forward or backward whirl frequencies:

- `0 (OFF, or NO)` - No sorting.
- `1 (ON, or YES)` - Sort. This value is the default.

**slope**

The slope of the line to be printed. This value must be positive.

- `SLOPE > 0` - In the stationary reference frame ( `RefFrame` = YES on the [[coriolis|CORIOLIS]] command), the line represents the number of excitations per revolution of the rotor. For example, `SLOPE` = 1 represents one excitation per revolution, usually resulting from unbalance.

  In the rotating reference frame ( `RefFrame` = NO on the [[coriolis|CORIOLIS]] command), the line represents the number of excitations per revolution of the rotor minus 1.

- `SLOPE = 0` - The line represents the stability threshold for stability values or logarithmic decrements printout ( `STABVAL` = 1, 2, or 3 )

**unit**

Specifies the unit of measurement for rotational angular velocities:

- `RDS` - Rotational angular velocities in radians per second (rad/s). This value is the default.
- `RPM` - Rotational angular velocities in revolutions per minute (RPMs).

**freqb**: The beginning, or lower end, of the frequency range of interest. The default is zero.

**cname**: The rotating component name.

**stabval**

Flag to plot the stability values:

- `0 (OFF, or NO)` - Plot the frequencies (the imaginary parts of the eigenvalues in Hz). This value is the default.
- `1 (ON, or YES)` - Plot the stability values (the real parts of the eigenvalues in Hz).
- `2` - Plot the inverse of the logarithmic decrements. A negative logarithmic decrement indicates stable motion.
- `3` - Plot the logarithmic decrements. A positive logarithmic decrement indicates stable motion and is consistent with API (American Petroleum Institute) standards.

For more information about complex eigenmodes and corresponding logarithmic decrements, see [Complex Eigensolutions](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool13.html#eq1c0f3d38-81fe-4aa4-860a-7a20afad6c74) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

**keyallfreq**

Key to specify if all frequencies above FREQB are plotted:

- `0 (OFF, or NO)` - A maximum of 10 frequencies are plotted. This value is the default.
- `1 (ON, or YES)` - All frequencies are plotted.

**keynegfreq**

Key to specify if the negative frequencies are plotted. It only applies to solutions obtained with the damped eigensolver ( `Method` = DAMP on the [[modopt|MODOPT]] command):

- `0 (OFF, or NO)` - Only positive frequencies are plotted. This value is the default.
- `1 (ON, or YES)` - Negative and positive frequencies are plotted.

## Notes

The following items are required when generating a Campbell diagram:

- Activate the Coriolis effect ( [[coriolis|CORIOLIS]] command) in the solution phase ( [[slashsolu|/SOLU]] ).
- Run a modal analysis using the QR damped ( [[modopt|MODOPT]],QRDAMP) or damped ( [[modopt|MODOPT]],DAMP) method. Complex eigenmodes are necessary ( [[modopt|MODOPT]],QRDAMP, `Cpxmod` = ON), and you must specify the number of modes to expand ( [[mxpand|MXPAND]] ).
- Define two or more load step results with an ascending order of rotational velocity ( [[omega|OMEGA]] or [[cmomega|CMOMEGA]] ).

In some cases where modes are not in the same order from one load step to the other, sorting the frequencies ( `Option` = 1) can help to obtain a correct plot. Sorting is based on the comparison between complex mode shapes calculated at two successive load steps.

At each load step, the application compares the mode shape to the loads at other load steps to determine whirl direction at the load step. If applicable, a label appears (in the plot legend) representing each whirl mode (BW for backward whirl and FW for forward whirl).

At each load step, the program checks for instability (based on the sign of the real part of the eigenvalue). The labels "stable" or "unstable" appear in the plot legend for each frequency curve.

The rotational velocities of a named component ( `Cname` ) are displayed on the X-axis.

For information on plotting a Campbell diagram for a prestressed structure, see [Solving for a Subsequent Campbell Analysis of a Prestressed Structure Using the Linear Perturbation Procedure](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTSOLPRESTRESS.html#rotdynsolu_CampbellPrestr)

For a usage example of the **PLCAMP** command, see [Campbell Diagram](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTCAMPDIAGS.html#rotgencamp2a)

Damped modal cyclic symmetry ( [[cyclic|CYCLIC]] ) analyses do not support the **PLCAMP** command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLCAMP.html
