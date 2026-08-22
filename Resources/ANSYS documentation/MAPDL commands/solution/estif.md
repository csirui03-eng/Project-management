---
apdl: "ESTIF"
method: estif
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.birth_and_death.BirthAndDeath.estif
generated: 2026-08-22
tags: [mapdl-command]
---

# ESTIF

PyMAPDL: `mapdl.estif(kmult='', **kwargs)`

Specifies the matrix multiplier for deactivated elements.

**Command default:**

Use 1.0E-6 as the multiplier.

## Parameters

**kmult**: Stiffness matrix multiplier for deactivated elements (defaults to 1.0E-6).

## Notes

Specifies the stiffness matrix multiplier for elements deactivated with the [[ekill|EKILL]] command (birth and death).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESTIF.html
