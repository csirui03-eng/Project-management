---
apdl: "NLGEOM"
method: nlgeom
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.nonlinear_options.NonlinearOptions.nlgeom
generated: 2026-08-22
tags: [mapdl-command]
---

# NLGEOM

PyMAPDL: `mapdl.nlgeom(key='', **kwargs)`

Includes large-deflection effects in a static or full transient analysis.

## Parameters

**key**

Large-deflection key:

- `OFF` - Ignores large-deflection effects (that is, a small-deflection analysis is specified). This option is the default.
- `ON` - Includes large-deflection (large rotation) effects or large strain effects, according to the element type.

## Notes

Large-deflection effects are categorized as either large deflection (or large rotation) or large strain, depending on the element type. These are listed (if available) under Special Features in the input data table for each element in the [Element Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_elem/Hlp_E_BIBLIO.html). When large deflection effects are included ( **NLGEOM**,ON), stress stiffening effects are also included automatically.

If used during the solution ( [[slashsolu|/SOLU]] ), this command is valid only within the first load step.

In a large-deflection analysis, pressure loads behave differently than other load types. For more information, see [Load Direction in a Large-Deflection Analysis](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_str/Hlp_G_STRnlbasin.html#aQAlprb2tlm).

The gyroscopic matrix (that occurs due to rotational angular velocity) does not support large- deflection effects. The theoretical formulations for the gyroscopic matrix support small deflection (linear formulation) only.

When large-deflection effects are included in a substructure or CMS transient analysis use pass, the [[outres|OUTRES]] command ignores `DSUBres` = ALL.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLGEOM.html
