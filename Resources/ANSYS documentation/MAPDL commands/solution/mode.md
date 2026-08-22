---
apdl: "MODE"
method: mode
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.mode
generated: 2026-08-22
tags: [mapdl-command]
---

# MODE

PyMAPDL: `mapdl.mode(mode='', isym='', **kwargs)`

Specifies the harmonic loading term for this load step.

## Parameters

**mode**: Number of harmonic waves around circumference for this harmonic loading term (defaults to 0).

**isym**

Symmetry condition for this harmonic loading term (not used when `MODE` = 0):

- `1` - Symmetric (UX, UY, ROTZ, TEMP use cosine terms; UZ uses sine term) (default).
- `-1` - Antisymmetric (UX, UY, ROTZ, TEMP use sine terms; UZ uses cosine term).

## Notes

Used with axisymmetric elements having nonaxisymmetric loading capability (for example, `PLANE25`, `SHELL61`, etc.). For analysis types [[antype|ANTYPE]],MODAL, HARMIC, TRANS, and SUBSTR, the term must be defined in the first load step and may not be changed in succeeding load steps.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MODE.html
