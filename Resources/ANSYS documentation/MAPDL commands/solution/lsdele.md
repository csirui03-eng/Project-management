---
apdl: "LSDELE"
method: lsdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.load_step_operations.LoadStepOperations.lsdele
generated: 2026-08-22
tags: [mapdl-command]
---

# LSDELE

PyMAPDL: `mapdl.lsdele(lsmin='', lsmax='', lsinc='', **kwargs)`

Deletes load step files.

## Parameters

**lsmin**, **lsmax**, **lsinc**: Range of load step files to be deleted, from `LSMIN` to `LSMAX` in steps of `LSINC`. `LSMAX` defaults to `LSMIN`, and `LSINC` defaults to 1. If `LSMIN` = ALL, all load step files are deleted (and `LSMAX` and `LSINC` are ignored). The load step files are assumed to be named `Jobname.Sn`, where `n` is a number assigned by the [[lswrite|LSWRITE]] command (01 -09,10,11, etc.). On systems with a 3-character limit on the extension, the S is dropped for numbers \> 99.

## Notes

Deletes load step files in the current directory (written by the [[lswrite|LSWRITE]] command).

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSDELE.html
