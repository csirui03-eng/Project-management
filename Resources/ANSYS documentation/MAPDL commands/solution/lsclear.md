---
apdl: "LSCLEAR"
method: lsclear
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_operations.LoadStepOperations.lsclear
generated: 2026-08-22
tags: [mapdl-command]
---

# LSCLEAR

PyMAPDL: `mapdl.lsclear(lab='', **kwargs)`

Clears loads and load step options from the database.

## Parameters

**lab**

Label identifying the data to be cleared:

- `SOLID` - Delete only solid model loads.
- `FE` - Delete only finite element loads.
- `INER` - Delete only inertia loads ( [[acel|ACEL]], etc.).
- `LFACT` - Initialize only load factors (on [[dcum|DCUM]], [[fcum|FCUM]], [[sfcum|SFCUM]], etc.).
- `LSOPT` - Initialize only load step options.
- `ALL` - Delete all loads and initialize all load step options and load factors.

## Notes

Loads are deleted, and load step options are initialized to their default values.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSCLEAR.html
