---
apdl: "FSUM"
method: fsum
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.fsum
generated: 2026-08-22
tags: [mapdl-command]
---

# FSUM

PyMAPDL: `mapdl.fsum(lab='', item='', **kwargs)`

Sums the nodal force and moment contributions of elements.

## Parameters

**lab**

Coordinate system in which to perform summation.

- `(blank)` - Sum all nodal forces in global Cartesian coordinate system (default).
- `RSYS` - Sum all nodal forces in the currently active RSYS coordinate system.

**item**

Selected set of nodes.

- `(blank)` - Sum all nodal forces for all selected nodes (default), excluding contact elements.
- `CONT` - Sum all nodal forces for contact nodes only.
- `BOTH` - Sum all nodal forces for all selected nodes, including contact elements.

## Notes

Sums and prints, in each component direction for the total selected node set, the nodal force and moment contributions of the selected elements attached to the node set. Selecting a subset of nodes ( [[nsel|NSEL]] ) and then issuing this command will give the total force acting on that set of nodes (default), excluding surface-to-surface, node-to-surface, line-to-line, and line-to-surface contact elements ( `TARGE169`, `TARGE170`, `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ).

Setting `ITEM` = CONT sums the nodal forces and moment contributions of the selected contact elements ( `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ). Setting `ITEM` = BOTH sums the nodal forces for all selected nodes, including contact elements.

Nodal forces associated with surface loads are not included. The effects of nodal coupling and constraint equations are ignored. Moment summations are about the global origin unless another point is specified with the [[spoint|SPOINT]] command. This vector sum is printed in the global Cartesian system unless it is transformed ( [[rsys|RSYS]] ) and a point is specified with the [[spoint|SPOINT]] command. By default, the sum is done in global Cartesian, and the resulting vector is transformed to the requested system.

The `LAB` = RSYS option transforms each of the nodal forces into the active coordinate system before summing and printing. The [[force|FORCE]] command can be used to specify which component (static, damping, inertia, or total) of the nodal load is to be used. This command output is included in the [[nforce|NFORCE]] command.

The command should not be used with axisymmetric elements because it might calculate a moment where none exists. Consider, for example, the axial load on a pipe modeled with an axisymmetric shell element. The reaction force on the end of the pipe is the total force (for the full 360 degrees) at that location. The net moment about the centerline of the pipe would be zero, but the program would incorrectly calculate a moment at the end of the element as the force multiplied by the radius.

The command is not valid for elements that operate solely within the nodal coordinate system with 1D option activated and rotated nodes ( [[nrotat|NROTAT]] ).

**Using FSUM with the NLGEOM Command** If you have activated large deflection ( [[nlgeom|NLGEOM]], ON ), the **FSUM** command generates the following message:

Summations based on final geometry and will not agree with solution reactions.

The message warns that the moment summations may not equal the real moment reactions. When calculating moment summations, the **FSUM** command assumes that the summation of rotations applies; however, it does not apply for large rotations, which require pseudovector representation to sum the rotations.

In contrast, the results for force reactions will be correct because they depend upon linear displacement vectors (which can be added).

**Using FSUM in a Spectrum or PSD Analysis ( ANTYPE, SPECTR)** When using **FSUM** in a spectrum analysis (after the combination file has been input through [[input|/INPUT]],,MCOM and when [[spopt|SPOPT]] has not been issued with `Elcalc` = YES during the spectrum analysis), or in a PSD analysis when postprocessing 1-sigma results (loadstep 3, 4, or 5), the following message will display in the printout header:

(Spectrum analysis summation is used)

This message means that the summation of the element nodal forces is performed prior to the combination of those forces. In this case, [[rsys|RSYS]] does not apply. The forces are in the nodal coordinate systems, and the vector sum is always printed in the global coordinate system.

The spectrum analysis summation is available when the element results are written to the mode file, `Jobname.mode` ( `MSUPkey` = Yes on the [[mxpand|MXPAND]] command).

Because modal displacements cannot be used to calculate contact element nodal forces, `ITEM` does not apply to spectrum and PSD analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FSUM.html
