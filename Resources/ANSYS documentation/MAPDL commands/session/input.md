---
apdl: "/INPUT"
method: input
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.input
generated: 2026-08-22
tags: [mapdl-command]
---

# /INPUT

PyMAPDL: `mapdl.input(fname='', ext='', dir_='', line='', log='', **kwargs)`

Switches the input file for the commands that follow.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to the current `Jobname` if `Ext` is specified.

**ext**: Filename extension (eight-character maximum).

**dir_**: Directory path (64 characters maximum). Defaults to current directory.

**line**

A value indicating either a line number in the file or a user-defined label in the file from which to begin reading the input file.

- `(blank), 0, or 1` - Begins reading from the top of the file (default).
- `LINE_NUMBER` - Begins reading from the specified line number in the file.
- `label` - Begins reading from the first line beginning with the matching user-defined label : `label` (beginning with a colon (:), 8 characters maximum).

**log**

Indicates whether secondary input from this command should be recorded in the command log ( `File.LOG` ) and the database log:

- `0` - Record only the **/INPUT** command on the log (default).
- `1` - Record commands in the specified secondary file as they are executed.

## Notes

Switches the input file for the next commands. Commands are read from this file until an end-of-file or another file switching directive is read. An end-of-file occurs after the last record of the file or when a `/EOF` command is read. An automatic switch back one level (to the previous file) occurs when an end-of-file is encountered. Twenty levels of nested file switching are allowed. Note that files including `*DO`, [[use|*USE]], [[ulib|*ULIB]], and the "Unknown Command" Macro have less nesting available because each of these operations also uses a level of file switching. For an interactive run, a **/INPUT**,TERM switches to the terminal for the next input. A `/EOF` read from the terminal then switches back to the previous file. A **/INPUT** (with a blank second field) switches back to the primary input file.

Setting `LOG` = 1 on **/INPUT** causes all commands read from the specified file to be recorded in the command log ( `File.LOG` ) and the internal database command log ( [[lgwrite|LGWRITE]] ). This option is recommended if the log file will be used later. The `LOG` = 1 option is only valid when the **/INPUT** occurs in the primary input file. Using `LOG` = 1 on a nested **/INPUT** or on a **/INPUT** within a do-loop will have no effect (that is, commands in the secondary input file are not written to the command log).

The `Dir` option is optional as the directory path can be included directly in `Fname`.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INPUT.html
