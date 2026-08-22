---
apdl: "LVSCALE"
method: lvscale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.lvscale
generated: 2026-08-22
tags: [mapdl-command]
---

# LVSCALE

PyMAPDL: `mapdl.lvscale(fact='', ldstep='', **kwargs)`

Scales the load vector for mode-superposition analyses.

## Parameters

**fact**: Scale factor applied to both the real and imaginary (if they exist) components of the load vector. Defaults to 0.0.

**ldstep**: Specifies the load step number from the modal analysis ( [[modcont|MODCONT]],ON). It corresponds to the load vector number. Defaults to 1. The maximum admissible value is the number of vectors written in the `Jobname.MODE` file.

## Notes

Specifies the scale factor for the load vector that was created in a modal ( [[antype|ANTYPE]],MODAL) analysis. Applies only to the mode-superposition transient analysis ( [[antype|ANTYPE]],TRANS), mode- superposition harmonic analysis ( [[antype|ANTYPE]],HARMIC), random vibration analysis ( [[antype|ANTYPE]] ,SPECTR with [[spopt|SPOPT]],PSD), and multiple point response spectrum analysis ( [[antype|ANTYPE]] ,SPECTR with [[spopt|SPOPT]],MPRS). For PSD and MPRS analyses, **LVSCALE** is only applicable for pressure loading.

The **LVSCALE** command supports tabular boundary conditions (%TABNAME_X%) for `FACT` input values only as a function of time in the mode-superposition transient ( [[antype|ANTYPE]],TRANS) or as a function of frequency in mode-superposition harmonic ( [[antype|ANTYPE]],HARMIC).

[MPC contact](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ctec/Hlp_ctec_restmpc.html) generates constraint equations that can include constant terms (included on the right-hand side of the system equation). The **LVSCALE** command scales the constant terms.

In mode-superposition transient and harmonic analyses, all of the load vectors need to be scaled in the first load step. Use a zero scale factor if they are not actually used in this first load step. Similarly, in random vibration and multipoint response spectrum analyses, all of the load vectors need to be scaled in the first participation factor calculation ( [[pfact|PFACT]] ). Use a zero scale factor if they are not actually used for the first input table.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LVSCALE.html
