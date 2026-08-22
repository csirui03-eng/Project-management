---
apdl: "ASOL"
method: asol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.analysis_options.AnalysisOptions.asol
generated: 2026-08-22
tags: [mapdl-command]
---

# ASOL

PyMAPDL: `mapdl.asol(lab='', opt='', **kwargs)`

Specifies the acoustic solver with scattered field formulation.

## Parameters

**lab**

Acoustic solver specification (no default):

- `SCAT` - Set acoustic solver to the scattered field formulation.

**opt**

Option identifying an acoustic solver status:

- `OFF` - Deactivate the specified acoustic solver (default).
- `ON` - Activate the specified acoustic solver.

## Notes

Use the **ASOL** command to activate the specified acoustic solution process.

The scattered option ( `Lab` = SCAT) sets the acoustic solver to the scattered-pressure field formulation.

Issue the [[awave|AWAVE]] command to define the incident pressure p <sup>inc</sup>. If the [[awave|AWAVE]] command is defined with `Opt2` = INT, the acoustic solver is set to the scattered field formulation regardless of the **ASOL** command issued.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASOL.html
