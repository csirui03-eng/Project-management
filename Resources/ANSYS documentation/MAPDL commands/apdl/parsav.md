---
apdl: "PARSAV"
method: parsav
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.parsav
generated: 2026-08-22
tags: [mapdl-command]
---

# PARSAV

PyMAPDL: `mapdl.parsav(lab='', fname='', ext='', **kwargs)`

Writes parameters to a file.

## Parameters

**lab**

Write operation:

- `SCALAR` - Write only scalar parameters (default).
- `ALL` - Write scalar and array parameters. Parameters may be numeric or alphanumeric.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to PARM if `Fname` is blank.

## Notes

Writes the current parameters to a coded file. Previous parameters on this file, if any, will be overwritten. The parameter file may be read with the [[parres|PARRES]] command.

**PARSAV** / [[parres|PARRES]] operations truncate some long decimal strings, and can cause differing values in your solution data when other operations are performed. A good practice is to limit the number of decimal places you will use before and after these operations.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PARSAV.html
