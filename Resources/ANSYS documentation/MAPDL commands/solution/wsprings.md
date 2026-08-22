---
apdl: "WSPRINGS"
method: wsprings
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.misc_loads.MiscLoads.wsprings
generated: 2026-08-22
tags: [mapdl-command]
---

# WSPRINGS

PyMAPDL: `mapdl.wsprings(**kwargs)`

Creates weak springs on corner nodes of a bounding box of the currently selected elements.

## Notes

This command invokes a predefined Mechanical APDL macro that is used during the import of loads from the ADAMS program into Mechanical APDL.

The command creates weak springs on the corner nodes of the bounding box of the currently selected elements. The six nodes of the bounding box are attached to ground using `COMBIN14` elements. The stiffness is chosen as a small number and can be changed by changing the real constants of the `COMBIN14` elements.

The command works only for models that have a geometric extension in two or three dimensions. One- dimensional problems (pure beam in one axis) are not supported.

For more information about how **WSPRINGS** is used during the transfer of loads from the ADAMS program to Mechanical APDL, see [Import Loads into Mechanical APDL](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_substr/advtrans12902.html#advimport).

> Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WSPRINGS.html
