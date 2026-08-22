---
apdl: "/GRESUME"
method: gresume
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gresume
generated: 2026-08-22
tags: [mapdl-command]
---

# /GRESUME

PyMAPDL: `mapdl.gresume(fname='', ext='', **kwargs)`

Sets graphics settings to the settings on a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to GSAV if `Fname` is blank.

## Notes

Causes a file to be read to reset the graphics slash (/) commands as they were at the last [[gsave|/GSAVE]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GRESUME.html
