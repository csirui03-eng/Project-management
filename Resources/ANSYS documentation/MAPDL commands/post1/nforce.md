---
apdl: "NFORCE"
method: nforce
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.special_purpose.SpecialPurpose.nforce
generated: 2026-08-22
tags: [mapdl-command]
---

# NFORCE

PyMAPDL: `mapdl.nforce(item='', **kwargs)`

Sums the nodal forces and moments of elements attached to nodes.

## Parameters

**item**

Specifies the selected set of nodes for summing forces and moments for contact elements.

- `(blank)` - Sums the nodal forces of elements for all selected nodes and excludes contact elements (elements 169-177).
- `CONT` - Sums the nodal forces of elements for contact nodes only.
- `BOTH` - Sums the nodal forces of elements for all selected nodes, including contact elements.

## Notes

Sums and prints, in each component direction for each selected node, the nodal force and moment contributions of the selected elements attached to the node. If all elements are selected, the sums are usually zero except where constraints or loads are applied. The nodal forces and moments may be displayed ( [[pbc|/PBC]],FORC and [[pbc|/PBC]],MOME). Use [[presol|PRESOL]] to print nodal forces and moments on an element-by-element basis. You can use the [[force|FORCE]] command to specify which component (static, damping, inertia, or total) of the nodal load is to be used. Nodal forces associated with surface loads are not included.

This vector sum is printed in the global Cartesian system. Moment summations are about the global origin unless another point is specified with the [[spoint|SPOINT]] command. The summations for each node are printed in the global Cartesian system unless transformed ( [[rsys|RSYS]] ). This command is generally not applicable to axisymmetric models because moment information from the NFORCE command is not correct for axisymmetric elements.

Selecting a subset of elements ( [[esel|ESEL]] ) and then issuing this command will give the forces and moments required to maintain equilibrium of that set of elements. The effects of nodal coupling and constraint equations are ignored. The option `ITEM` = CONT provides the forces and moments for the contact elements ( `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ). Setting `ITEM` = BOTH provides the forces and moments for all selected nodes, including contact elements.

This command also includes the [[fsum|FSUM]] command function which vectorially sums and prints, in each component direction for the total selected node set, the nodal force and moment contributions of the selected elements attached to the selected node set.

**Using NFORCE in a Spectrum or PSD Analysis ( ANTYPE, SPECTR)** When using **NFORCE** in a spectrum analysis (after the combination file has been input through [[input|/INPUT]],,MCOM and when [[spopt|SPOPT]] has not been issued with `Elcalc` = YES during the spectrum analysis), or in a PSD analysis when postprocessing 1-sigma results (loadstep 3, 4, or 5), the following message will display in the printout header:

(Spectrum analysis summation is used)

This message means that the summation of the element nodal forces is performed prior to the combination of those forces. In this case, [[rsys|RSYS]] does not apply. The forces are in the nodal coordinate systems, and the vector sum is always printed in the global coordinate system.

The spectrum analysis summation is available when the element results are written to the mode file, `Jobname.MODE` ( `MSUPkey` = Yes on the [[mxpand|MXPAND]] command).

Because modal displacements cannot be used to calculate contact element nodal forces, `ITEM` does not apply to spectrum and PSD analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NFORCE.html
