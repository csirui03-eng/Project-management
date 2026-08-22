---
apdl: "*CFWRITE"
method: cfwrite
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.cfwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# *CFWRITE

PyMAPDL: `mapdl.cfwrite(command='', **kwargs)`

Writes a Mechanical APDL command (or similar string) to a "command" file.

## Parameters

**command**: Command or string to be written. The standard command form of a label followed by arguments separated by commas is assumed. `Command` may be a parameter assignment (for example, **\*CFWRITE**, A = 5).

## Notes

### Argument descriptions

- `command : str` - Command or string to be written. The standard command form of a label followed by arguments separated by commas is assumed. `Command` may be a parameter assignment (for example, **\*CFWRITE**, A = 5).

Writes a Mechanical APDL command (or similar string) to the file opened via [[cfopen|*CFOPEN]]. The `Command` string is not executed (except that numeric and character parameter substitution and operations (with imbedded \*, /, \>, etc. characters) are performed before writing).

When used with [[get|*GET]] results and parameter substitution, a command can be created from results and then read back into the Mechanical APDL program (or used elsewhere). For example, if the command **\*CFWRITE**,BF,NNUM,TEMP,TVAL is used in a do-loop, where TVAL is a parameter value returned from the [[get|*GET]] operation and NNUM is a specified or returned parameter value, a series of [[bf|BF]] commands, with numerical values substituted for the two parameters, will be written.

To create a file without parameter substitution, issue [[create|*CREATE]].

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CFWRITE.html
