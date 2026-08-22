---
apdl: "/INQUIRE"
method: inquire
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.inquire
generated: 2026-08-22
tags: [mapdl-command]
---

# /INQUIRE

PyMAPDL: `mapdl.inquire(strarray='', func='', **kwargs)`

Returns system information to a parameter.

## Parameters

**strarray**: Name of the "string array" parameter that will hold the returned values. String array parameters are similar to character arrays, but each array element can be as long as 248 characters. If the string parameter does not exist, it will be created.

**func**

Specifies the type of file information returned:

- `EXIST` - Returns a 1 if the specified file exists, and 0 if it does not.
- `DATE` - Returns the date stamp of the specified file in the format `yyyymmdd.hhmmss`.
- `SIZE` - Returns the size of the specified file in MB.
- `WRITE` - Returns the status of the write attribute. A 0 denotes no write permission while a 1 denotes write permission.
- `READ` - Returns the status of the read attribute. A 0 denotes no read permission while a 1 denotes read permission.
- `EXEC` - Returns the status of the execute attribute (this has meaning only on Linux). A 0 denotes no execute permission while a 1 denotes execute permission.
- `LINES` - Returns the number of lines in an ASCII file.

## Notes

The **/INQUIRE** command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INQUIRE.html
