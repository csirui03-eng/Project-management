---
apdl: "*CFOPEN"
method: cfopen
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.cfopen
generated: 2026-08-22
tags: [mapdl-command]
---

# *CFOPEN

PyMAPDL: `mapdl.cfopen(fname='', ext='', loc='', **kwargs)`

Opens a "command" file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to CMD if `Fname` is blank.

**loc**

Determines whether existing file will be overwritten or appended:

- `(blank)` - The existing file will be overwritten.
- `APPEND` - The file will be appended to the existing file.

## Notes

### Argument descriptions

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

\* `ext : str` - Filename extension (eight-character maximum). The extension defaults to CMD if `Fname` is blank.

- `loc : str` - Determines whether existing file will be overwritten or appended:
  - `(blank)` - The existing file will be overwritten.
  - `APPEND` - The file will be appended to the existing file.

Mechanical APDL commands specified by the [[cfwrite|*CFWRITE]] command are written to the file opened by **\*CFOPEN**. Data processed with the [[vwrite|*VWRITE]] command are also written to this file if the file is open when the [[vwrite|*VWRITE]] command is issued.

Issue the [[cfclos|*CFCLOS]] command to close the command file.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CFOPEN.html
