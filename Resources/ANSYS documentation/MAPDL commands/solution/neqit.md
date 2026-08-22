---
apdl: "NEQIT"
method: neqit
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.neqit
generated: 2026-08-22
tags: [mapdl-command]
---

# NEQIT

PyMAPDL: `mapdl.neqit(neqit='', forcekey='', **kwargs)`

Specifies the maximum number of equilibrium iterations for nonlinear analyses.

## Parameters

**neqit**: Maximum number of equilibrium iterations allowed each substep.

**forcekey**

One iteration forcing key:

- `FORCE` - Forces one iteration per substep. Leave this field blank otherwise.

Using one iteration per substep may result in unconverged solutions for nonlinear analysis, and the program may not indicate divergence in this case. This option is intended primarily for use by the Ansys Workbench interface. Keep in mind that forcing one iteration per substep is only recommended under very specific conditions; for example, nonlinearity in bonded penalty type contact. Under these conditions the solution typically converges in one iteration.

## Notes

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NEQIT.html
