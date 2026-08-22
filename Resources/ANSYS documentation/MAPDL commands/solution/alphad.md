---
apdl: "ALPHAD"
method: alphad
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.alphad
generated: 2026-08-22
tags: [mapdl-command]
---

# ALPHAD

PyMAPDL: `mapdl.alphad(value='', **kwargs)`

Defines the mass matrix multiplier for damping.

## Parameters

**value**: Mass matrix multiplier for damping.

## Notes

This command defines the mass matrix multiplier (equation omitted) used to form the viscous damping matrix (equation omitted), where (equation omitted) is the mass matrix.

Values of (equation omitted) can also be input as a material property ( [[mp|MP]],ALPD or [[tb|TB]],SDAMP,,,,ALPD). If ALPD in either form is included, the ALPD value is added to the **ALPHAD** value as appropriate. (See [Material Damping](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mat/mat_matdamping.html#) [Damping Matrices](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_tool3.html#) [[antype|ANTYPE]],STATIC) or buckling ( [[antype|ANTYPE]],BUCKLE) analyses.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ALPHAD.html
