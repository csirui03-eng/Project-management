---
apdl: "*CREATE"
method: create
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.create
generated: 2026-08-22
tags: [mapdl-command]
---

# *CREATE

PyMAPDL: `mapdl.create(fname='', ext='', **kwargs)`

Opens (creates) a macro file.

> [!WARNING]
> This command must be run using `non_interactive <ansys.mapdl.core.Mapdl.non_interactive>`. Please visit [Unsupported Interactive Commands](https://mapdl.docs.pyansys.com/version/stable/user_guide/mapdl.html#unsupported-interactive-commands) for further information.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. Do not use a directory path if file is to be read with the macro `Name` option of the [[use|*USE]] command.

**ext**: Filename extension (eight-character maximum). `Ext` should not be used if file is to be read with the macro `Name` option of the [[use|*USE]] command.

## Notes

### Argument descriptions

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. Do not use a directory path if file is to be read with the macro `Name` option of the [[use|*USE]] command.

\* `ext : str` - Filename extension (eight-character maximum). `Ext` should not be used if file is to be read with the macro `Name` option of the [[use|*USE]] command.

See the [[use|*USE]] command for a discussion of macros. All commands following the **\*CREATE** command, up to the [[end|*END]] command, are written to the specified file without being executed. An existing file of the same name, if any, will be overwritten. Parameter values are not substituted for parameter names in the commands when the commands are written to the file. Use [[cfwrite|*CFWRITE]] to create a file if this is desired. The resulting macro may be executed with a [[use|*USE]] command (which also allows parameters to be passed into the macro) or a [[input|/INPUT]] command (which does not allow parameters to be passed in). Several macros may be stacked into a library file ( [[ulib|*ULIB]] ). You cannot use **\*CREATE** within a DO loop.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CREATE.html
