---
apdl: "CECMOD"
method: cecmod
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_options.LoadStepOptions.cecmod
generated: 2026-08-22
tags: [mapdl-command]
---

# CECMOD

PyMAPDL: `mapdl.cecmod(neqn='', const='', **kwargs)`

Modifies the constant term of a constraint equation during solution.

## Parameters

**neqn**: Reference number of constraint equation.

**const**: New value of the constant term of equation.

## Notes

Other terms of the constraint equation cannot be changed during the solution phase, but must be defined or changed within PREP7 prior to the solution. See the [[ce|CE]] command for details.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CECMOD.html
