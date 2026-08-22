---
apdl: "*TREAD"
method: tread
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.tread
generated: 2026-08-22
tags: [mapdl-command]
---

# *TREAD

PyMAPDL: `mapdl.tread(par='', fname='', ext='', nskip='', **kwargs)`

Reads data from an external file into a table array parameter.

## Parameters

**par**: Table array parameter name as defined by the [[dim|*DIM]] command.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. File name has no default.

**ext**: Filename extension (eight-character maximum). Extension has no default.

**nskip**: Number of comment lines at the beginning of the file being read that will be skipped during the reading. Default = 0.

## Notes

### Argument descriptions

- `par : str` - Table array parameter name as defined by the [[dim|*DIM]] command.

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. File name has no default.

- `ext : str` - Filename extension (eight-character maximum). Extension has no default.
- `nskip : str` - Number of comment lines at the beginning of the file being read that will be skipped during the reading. Default = 0.

Use this command to read in a table of data from an external file into a table array parameter. The external file may be created using a text editor or by an external application or program. To be used by **\*TREAD**, the external file's encoding format must be UTF-8, and the file must be in tab-delimited, blank-delimited, or comma-delimited format. The TABLE type array parameter must be defined before you can read in an external file. See [[dim|*DIM]] for more information.

This command is not applicable to 4- or 5-D tables.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TREAD.html
