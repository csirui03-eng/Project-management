---
apdl: "EXPSOL"
method: expsol
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.expsol
generated: 2026-08-22
tags: [mapdl-command]
---

# EXPSOL

PyMAPDL: `mapdl.expsol(lstep='', sbstep='', timfrq='', elcalc='', **kwargs)`

Specifies the solution to be expanded for mode-superposition analyses or substructure analyses.

## Parameters

**lstep**, **sbstep**: Expand the solution identified as load step `LSTEP` and substep `SBSTEP`.

**timfrq**: As an alternative to `LSTEP` and `SBSTEP`, expand the solution at, or nearest to, the time value TIMFRQ (for [[antype|ANTYPE]],TRANS or [[antype|ANTYPE]],SUBSTR) or frequency value `TIMFRQ` (for [[antype|ANTYPE]],HARMIC). `LSTEP` and `SBSTEP` should be blank.

**elcalc**

Element calculation key:

- `YES` - Calculate element results, nodal loads, and reaction loads.
- `NO` - Do not calculate these items.

## Notes

Specifies the solution to be expanded from analyses that use the mode-superposition method ( [[antype|ANTYPE]],HARMIC or TRANS) or substructuring ( [[antype|ANTYPE]],SUBSTR). Use the [[numexp|NUMEXP]] command to expand a group of solutions.

The resulting results file will maintain the same load step, substep, and time (or frequency) values as the requested solution to be expanded.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EXPSOL.html
