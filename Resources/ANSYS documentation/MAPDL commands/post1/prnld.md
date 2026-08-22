---
apdl: "PRNLD"
method: prnld
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prnld
generated: 2026-08-22
tags: [mapdl-command]
---

# PRNLD

PyMAPDL: `mapdl.prnld(lab='', tol='', item='', **kwargs)`

Prints the summed element nodal loads.

## Parameters

**lab**

Nodal reaction load type. If blank, use the first ten of all available labels. Valid labels are:

- **Structural force labels** : FX, FY or FZ (forces); F (FX, FY and FZ); MX, MY or MZ (moments); M (MX, MY and MZ).
- **Thermal force labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid force labels** : FLOW (fluid flow); VFX, VFY and VFZ (fluid "forces"); VF (VFX, VFY and VFZ).
- **Electric force labels** : AMPS (current flow); CHRG (charge); CURT (current); VLTG (voltage drop).
- **Magnetic force labels** : FLUX (magnetic flux); CSGZ (magnetic current segment).
- **Diffusion label** : RATE (diffusion flow rate).

**tol**

Tolerance value about zero within which loads are not printed, as follows:

- `> 0` - Relative tolerance about zero within which loads are not printed. In this case, the tolerance is `TOL` \* `Load`, where `Load` is the absolute value of the maximum load on the selected nodes.
- `0` - Print all nodal loads.
- `> 0` - Absolute tolerance about zero within which loads are not printed.

Defaults to 1.0E-9 times the absolute value of the maximum load on the selected nodes.

**item**

Selected set of nodes.

- `(blank)` - Prints the summed element nodal loads for all selected nodes (default), excluding contact elements.
- `CONT` - Prints the summed element nodal loads for contact nodes only.
- `BOTH` - Prints the summed element nodal loads for all selected nodes, including contact nodes.

## Notes

Prints the summed element nodal loads (forces, moments, heat flows, flux, etc.) for the selected nodes in the sorted sequence. Results are in the global Cartesian coordinate directions unless transformed ( [[rsys|RSYS]] ). Zero values (within a tolerance range) are not printed. Loads applied to a constrained degree of freedom are not included. The [[force|FORCE]] command can be used to define which component of the nodal load is to be used (static, damping, inertia, or total).

By default, **PRNLD** excludes elements `TARGE169` - `CONTA177`. Setting `ITEM` = CONT will only account for nodal forces on selected contact elements ( `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` ). Setting `ITEM` = BOTH will account for nodal forces on all selected nodes, including contact nodes.

**Using PRNLD in a Spectrum or PSD Analysis ( ANTYPE, SPECTR)** When using **PRNLD** in a spectrum analysis (after the combination file has been input through [[input|/INPUT]],,MCOM and when [[spopt|SPOPT]] has not been issued with `Elcalc` = YES during the spectrum analysis), or in a PSD analysis when postprocessing 1-sigma results (loadstep 3, 4, or 5), the following message will display in the printout header:

(Spectrum analysis summation is used)

This message means that the summation of the element nodal forces is performed prior to the combination of those forces. In this case, [[rsys|RSYS]] does not apply. The forces are in the nodal coordinate systems, and the vector sum is always printed in the global coordinate system.

The spectrum analysis summation is available when the element results are written to the mode file, `Jobname.mode` ( `MSUPkey` = Yes on the [[mxpand|MXPAND]] command).

Because modal displacements cannot be used to calculate contact element nodal forces, `ITEM` does not apply to spectrum and PSD analyses.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRNLD.html
