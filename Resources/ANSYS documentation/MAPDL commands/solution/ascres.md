---
apdl: "ASCRES"
method: ascres
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.ascres
generated: 2026-08-22
tags: [mapdl-command]
---

# ASCRES

PyMAPDL: `mapdl.ascres(opt='', **kwargs)`

Specifies the output type for an acoustic scattering analysis.

## Parameters

**opt**

Output option:

- `TOTAL` - Output the total pressure field (default).
- `SCAT` - Output the scattered pressure field.

## Notes

Use the **ASCRES** command to specify the output type for an acoustic scattering analysis.

The scattered option ( `Opt` = SCAT) provides a scattered pressure output, p<sub>sc</sub>, required for calculating target strength (TS).

The default behavior ( `Opt` = TOTAL) provides a sum of the incident and scattering fields, p <sup>total</sup> = p <sup>inc</sup> + p <sup>sc</sup>.

Issue the [[awave|AWAVE]] command to define the incident pressure p <sup>inc</sup>. If the [[awave|AWAVE]] command is defined with `Opt2` = INT, only the total pressure field is output regardless of the **ASCRES**, `Opt` command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASCRES.html
