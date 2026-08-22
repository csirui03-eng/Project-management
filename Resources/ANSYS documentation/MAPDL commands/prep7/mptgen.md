---
apdl: "MPTGEN"
method: mptgen
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.materials.Materials.mptgen
generated: 2026-08-22
tags: [mapdl-command]
---

# MPTGEN

PyMAPDL: `mapdl.mptgen(stloc='', num='', tstrt='', tinc='', **kwargs)`

Adds temperatures to the temperature table by generation.

## Parameters

**stloc**: Starting location in table for generating temperatures. Defaults to last location filled + 1.

**num**: Number of temperatures to be generated (1-100).

**tstrt**: Temperature assigned to `STLOC` location.

**tinc**: Increment previous temperature by `TINC` and assign to next location until all `NUM` locations are filled.

## Notes

Adds temperatures to the temperature table by generation. May be used in combination (or in place of) the [[mptemp|MPTEMP]] command.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPTGEN.html
