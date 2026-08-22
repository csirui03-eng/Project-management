---
apdl: "FTWRITE"
method: ftwrite
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1._fatigue.Fatigue.ftwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# FTWRITE

PyMAPDL: `mapdl.ftwrite(fname='', ext='', **kwargs)`

Writes all currently stored fatigue data on a file.

## Parameters

**fname**: File name (defaults to `Jobname` ).

**ext**: File name extension (defaults to FATG if `Fname` ).

## Notes

Data are written in terms of the equivalent POST1 fatigue commands (FTSIZE, FL, FS, etc.) which you can then edit and resubmit to POST1 (via the [[input|/INPUT]] command).

After you have created a fatigue data file, each subsequent use of the FTWRITE command overwrites the contents of that file.

> [!WARNING]
> This command is archived in the latest version of the software.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FTWRITE.html
