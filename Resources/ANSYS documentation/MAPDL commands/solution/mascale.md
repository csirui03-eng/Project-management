---
apdl: "MASCALE"
method: mascale
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.dynamic_options.DynamicOptions.mascale
generated: 2026-08-22
tags: [mapdl-command]
---

# MASCALE

PyMAPDL: `mapdl.mascale(massfact='', **kwargs)`

Activates scaling of the entire system matrix.

## Parameters

**massfact**: Scaling factor (\> 0) for the mass matrix. Default = 1.0.

## Notes

This command is supported in the first load step of the analysis only.

The following features are not affected by the scaling:

- Ocean loading ( [Applying Ocean Loading from a Hydrodynamic Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_adv/advOLexample.html)
- Steady-state rolling ( [[sstate|SSTATE]] )

The mass-related information (mass, center of mass, and mass moments of inertia) printed in the mass summary is based on unscaled mass properties.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MASCALE.html
