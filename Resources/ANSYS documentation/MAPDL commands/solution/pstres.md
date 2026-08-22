---
apdl: "PSTRES"
method: pstres
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.pstres
generated: 2026-08-22
tags: [mapdl-command]
---

# PSTRES

PyMAPDL: `mapdl.pstres(key='', **kwargs)`

Specifies whether prestress effects are calculated or included.

## Parameters

**key**

Prestress key:

- `OFF` - Do not calculate (or include) prestress effects (default).
- `ON` - Calculate (or include) prestress effects.

## Notes

The **PSTRES** command specifies whether or not prestress effects are to be calculated or included. The command should be issued after the [[antype|ANTYPE]] command.

Prestress effects are calculated in a static or transient analysis for inclusion in a buckling, modal, harmonic (Method = FULL), or substructure generation analysis. If used in the solution processor ( [[slashsolu|/SOLU]] ), this command is valid only within the first load step.

If you apply thermal body forces during a static analysis to calculate prestress effects, do not delete the forces during any subsequent full harmonic analyses. If you delete the thermal body forces, the thermal prestress effects will not be included in the harmonic analysis. Temperature loads used to define the thermal prestress will also be used in the full harmonic analysis as sinusoidally time-varying temperature loads.

A prestress effect applied with non-follower loads resists rigid body rotation of the model. For example, an unsupported beam with axial tensile forces applied to both ends will have two nonzero rotational rigid body modes.

If tabular loading ( [[dim|*DIM]], TABLE ) was used in the prestress static analysis step, the corresponding value of [[time|TIME]] will be used for tabular evaluations in the modal analysis.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSTRES.html
