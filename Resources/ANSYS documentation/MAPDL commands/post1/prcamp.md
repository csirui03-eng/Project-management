---
apdl: "PRCAMP"
method: prcamp
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.prcamp
generated: 2026-08-22
tags: [mapdl-command]
---

# PRCAMP

PyMAPDL: `mapdl.prcamp(option='', slope='', unit='', freqb='', cname='', stabval='', keyallfreq='', keynegfreq='', keywhirl='', **kwargs)`

Prints Campbell diagram data for applications involving rotating structure dynamics.

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

Flag to print the stability values:

- `0 (OFF, or NO)` - Print the frequencies (the imaginary parts of the eigenvalues in Hz). This value is the default.
- `1 (ON, or YES)` - Print the stability values (the real parts of the eigenvalues in Hz).
- `2` - Print the inverse of the logarithmic decrements. A negative logarithmic decrement indicates stable motion.
- `3` - Print the logarithmic decrements. A positive logarithmic decrement indicates stable motion and is consistent with API (American Petroleum Institute) standards.

For more information about complex eigenmodes and corresponding logarithmic decrements, see [Complex Eigensolutions](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool13.html#eq1c0f3d38-81fe-4aa4-860a-7a20afad6c74) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html).

**keyallfreq**

Key to specify if all frequencies above FREQB are printed out:

- `0 (OFF, or NO)` - A maximum of 10 frequencies are printed out. They correspond to the frequencies displayed via the [[plcamp|PLCAMP]] command. This value is the default.
- `1 (ON, or YES)` - All frequencies are printed out.

**keynegfreq**

Key to specify if the negative frequencies are printed out. It only applies to solutions obtained with the damped eigensolver ( `Method` =DAMP on the [[modopt|MODOPT]] command):

- `0 (OFF, or NO)` - Only positive frequencies are printed out. This value is the default.
- `1 (ON, or YES)` - Negative and positive frequencies are printed out.

**keywhirl**

Flag to print the whirl and instability keys for each load step:

- `0 (OFF, or NO)` - Print the whirl for the last load step. This value is the default.
- `1 (ON, or YES)` - Print the whirl and instability keys for each load step.

## Notes

The following items are required when generating a Campbell diagram:

- Activate the Coriolis effect ( [[coriolis|CORIOLIS]] command) in the solution phase ( [[slashsolu|/SOLU]] ).
- Run a modal analysis using the QR damped ( [[modopt|MODOPT]],QRDAMP) or damped ( [[modopt|MODOPT]],DAMP) method. Complex eigenmodes are necessary ( [[modopt|MODOPT]],QRDAMP, `Cpxmod` = ON), and you must specify the number of modes to expand ( [[mxpand|MXPAND]] ).
- Define two or more load step results with an ascending order of rotational velocity ( [[omega|OMEGA]] or [[cmomega|CMOMEGA]] ).

In some cases where modes are not in the same order from one load step to the other, sorting the frequencies ( `Option` = 1) can help to obtain a correct printout. Sorting is based on the comparison between complex mode shapes calculated at two successive load steps.

At each load step, the application compares the mode shape to the loads to determine the whirl direction. If applicable, a label appears (on the rows of output data) representing the whirl mode (BW for backward whirl and FW for forward whirl).

If you specify a non-zero slope ( `SLOPE` \> 0), the command prints the critical speeds corresponding to the intersection points of the frequency curves and the added line. In the case of a named component ( `Cname` ), critical speeds relate to the rotational velocity of the component. Critical speeds are available only if the frequencies are printed ( STABVAL = OFF).

If you specify a zero slope ( `SLOPE` = 0), the command prints the stability threshold corresponding to the sign change of the stability values (or logarithmic decrements). In the case of a named component ( `Cname` ), stability thresholds relate to the rotational velocity of the component. Stability thresholds are available only if the stability values or logarithmic decrements are printed ( `STABVAL` = 1, 2, or 3 ).

At each load step, the program checks for instability (based on the sign of the real part of the eigenvalue). The label "U" appears on the printout for each unstable frequency.

If specified, the rotational velocities of the named component ( `Cname` ) are printed out along with the natural frequencies.

For information on printing a Campbell diagram for a prestressed structure, see [Solving for a Subsequent Campbell Analysis of a Prestressed Structure Using the Linear Perturbation Procedure](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTSOLPRESTRESS.html#rotdynsolu_CampbellPrestr)

For a usage example of the companion command [[plcamp|PLCAMP]] (used for plotting a Campbell diagram), see [Example: Campbell Diagram Analysis of a Simply Supported Beam](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ADVRSDSMP1.html#)

For more information on Campbell diagram generation, see [Campbell Diagram](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_rot/Hlp_G_ROTCAMPDIAGS.html#rotgencamp2a)

Damped modal cyclic symmetry ( [[cyclic|CYCLIC]] ) analyses do not support the **PRCAMP** command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRCAMP.html
