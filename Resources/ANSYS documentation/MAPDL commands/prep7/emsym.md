---
apdl: "EMSYM"
method: emsym
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.special_purpose.SpecialPurpose.emsym
generated: 2026-08-22
tags: [mapdl-command]
---

# EMSYM

PyMAPDL: `mapdl.emsym(nsect='', **kwargs)`

Specifies circular symmetry for electromagnetic sources.

## Parameters

**nsect**: The number of circular symmetry sections (defaults to 1).

## Notes

Specifies the number of times to repeat electromagnetic sources for circular symmetry. Applies to `SOURC36` elements and to coupled-field elements with electric current conduction results in the database. Sources are assumed to be equally spaced over 360° about the global Cartesian Z axis.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EMSYM.html
