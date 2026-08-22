---
apdl: "HROUT"
method: hrout
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.hrout
generated: 2026-08-22
tags: [mapdl-command]
---

# HROUT

PyMAPDL: `mapdl.hrout(reimky='', clust='', mcont='', engcalc='', **kwargs)`

Specifies the harmonic analysis output options.

## Parameters

**reimky**

Real/Imaginary print key:

- `ON` - Print complex displacements as real and imaginary components (default).
- `OFF` - Print complex displacements as amplitude and phase angle (degrees).

**clust**

Cluster option (for [[hropt|HROPT]],MSUP):

- `OFF` - Uniform spacing of frequency solutions (default).
- `ON` - Cluster frequency solutions about natural frequencies.

**mcont**

Mode contributions key (for [[hropt|HROPT]],MSUP):

- `OFF` - No print of mode contributions at each frequency (default).
- `ON` - Print mode contributions at each frequency.

**engcalc**

Additional element energies calculation key:

- `NO` - Do not calculate additional energies (default).
- `YES` - Calculate average, amplitude, and peak values for the following: stiffness and kinetic energies, damping energy, and work done by external loads.

## Notes

Specifies the harmonic analysis ( [[antype|ANTYPE]],HARMIC) output options. If used in SOLUTION, this command is valid only within the first load step. [[outpr|OUTPR]],NSOL must be specified to print mode contributions at each frequency.

If the calculation of additional energies is requested ( `EngCalc` = YES) in a mode-superposition harmonic analysis ( `Method` = MSUP on the [[hropt|HROPT]] command), work done by external loads is not calculated if `MSUPkey` = YES on the [[mxpand|MXPAND]] command. If `MSUPkey` = NO, work due to element loads is calculated, but not work due to nodal loads.

Only the `Reimky` argument is supported and applicable for frequency-sweep harmonic analyses using the [Krylov](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_Krysweep.html#str_Krylov_macros) or [Variational Technology](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/str_harmsweep.html#) Methods. All other arguments are ignored if the [[hropt|HROPT]] command has been issued with `Method` = KRYLOV, VT, or VTPA.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HROUT.html
