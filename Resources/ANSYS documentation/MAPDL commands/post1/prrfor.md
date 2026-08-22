---
apdl: "PRRFOR"
method: prrfor
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.results.Results.prrfor
generated: 2026-08-22
tags: [mapdl-command]
---

# PRRFOR

PyMAPDL: `mapdl.prrfor(lab='', **kwargs)`

Prints the constrained node reaction solution. Used with the [[force|FORCE]] command.

## Parameters

**lab**

Nodal reaction load type. If blank, use the first ten of all available labels. Valid labels are:

- **Structural force labels** : FX, FY or FZ (forces); F (FX, FY and FZ); MX, MY or MZ (moments); M (MX, MY and MZ).
- **Thermal force labels** : HEAT, HBOT, HE2, HE3,..., HTOP (heat flow).
- **Fluid force labels** : FLOW (fluid flow); VFX, VFY and VFZ (fluid forces); VF (VFX, VFY and VFZ).
- **Electric force labels** : AMPS (current flow); CHRG (charge); CURT (current); VLTG (voltage drop).
- **Magnetic force labels** : FLUX (magnetic flux); CSGZ (magnetic current segment); CURT (current), VLTG (voltage drop).
- **Diffusion labels** : RATE (diffusion flow rate).

## Notes

**PRRFOR** has the same functionality as the [[prrsol|PRRSOL]] command; use **PRRFOR** instead of [[prrsol|PRRSOL]] when a [[force|FORCE]] command has been issued.

In a non-spectrum analysis, if either contact or pretension elements exist in the model, **PRRFOR** uses the [[prrsol|PRRSOL]] command internally and the [[force|FORCE]] setting is ignored.

Because modal displacements cannot be used to calculate contact element nodal forces, those forces are not included in the spectrum and PSD analyses reaction solution. As a consequence, the **PRRFOR** command is not supported when constraints on contact element pilot nodes are present.

**PRRFOR** is not valid when using the amplitude or phase results set ( `KIMG` = AMPL or PHAS on the [[set|SET]] command). Use [[prrsol|PRRSOL]] instead.

**Using PRRFOR in a Spectrum or PSD Analysis ( ANTYPE,SPECTR)** When using **PRRFOR** in a spectrum analysis (after the combination file has been input through [[input|/INPUT]],,MCOM and when [[spopt|SPOPT]] has not been issued with `Elcalc` = YES during the spectrum analysis), or in a PSD analysis when postprocessing 1-sigma results (loadstep 3, 4, or 5), the following message will display in the printout header:

``` apdl
(Spectrum analysis summation is used)
```

This message means that the summation of the element nodal forces is performed prior to the combination of those forces. In this case, [[rsys|RSYS]] does not apply, and the reaction forces are in the nodal coordinate systems. Unlike [[prrsol|PRRSOL]], which retrieves the forces from the database, the **PRRFOR** command calculates the forces in the postprocessor.

The spectrum analysis summation is available when the element results are written to the mode file, `Jobname.mode` ( `MSUPkey` = Yes on [[mxpand|MXPAND]] ).

The spectrum analysis summation is not available after reading a load case ( [[lcwrite|LCWRITE]], [[lczero|LCZERO]], [[lcase|LCASE]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRRFOR.html
