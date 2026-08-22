---
apdl: "/GSAVE"
method: gsave
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gsave
generated: 2026-08-22
tags: [mapdl-command]
---

# /GSAVE

PyMAPDL: `mapdl.gsave(fname='', ext='', **kwargs)`

Saves graphics settings to a file for later use.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to GSAV if `Fname` is blank.

## Notes

This command does not save all graphics settings, but only those that may be reset by the [[slashreset|/RESET]] command. The database remains untouched. Use the [[gresume|/GRESUME]] command to read the file. Repeated use of the **/GSAVE** command overwrites the previous data on the file. The following commands are saved by **/GSAVE** :

(table not available in the PyMAPDL source, see the Ansys help page)

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GSAVE.html
