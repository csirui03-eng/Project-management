---
apdl: "LSSOLVE"
method: lssolve
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_operations.LoadStepOperations.lssolve
generated: 2026-08-22
tags: [mapdl-command]
---

# LSSOLVE

PyMAPDL: `mapdl.lssolve(lsmin='', lsmax='', lsinc='', **kwargs)`

Reads and solves multiple load steps.

## Parameters

**lsmin**, **lsmax**, **lsinc**: Range of load step files to be read and solved, from `LSMIN` to `LSMAX` in steps of `LSINC`. `LSMAX` defaults to `LSMIN`, and `LSINC` defaults to 1. If `LSMIN` is blank, a brief command description is displayed. The load step files are assumed to be named `Jobname.Sn`, where `n` is a number assigned by the [[lswrite|LSWRITE]] command (01- 09,10,11, etc.). On systems with a 3-character limit on the extension, the S is dropped for numbers \> 99.

## Notes

This command invokes a Mechanical APDL macro ( `LSSOLVE.MAC` ) to read and solve multiple load steps.

The macro loops through a series of load step files written by the [[lswrite|LSWRITE]] command.

This command cannot be used with the birth-death option, does not support cyclic symmetry analysis, and does not support restarts.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSSOLVE.html
