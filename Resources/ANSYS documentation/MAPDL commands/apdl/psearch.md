---
apdl: "/PSEARCH"
method: psearch
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.psearch
generated: 2026-08-22
tags: [mapdl-command]
---

# /PSEARCH

PyMAPDL: `mapdl.psearch(pname='', **kwargs)`

Specifies a directory to be searched for "unknown command" macro files.

## Parameters

**pname**: Path name (64 characters maximum, and must include the final delimiter) of the middle directory to be searched. Defaults to the user home directory. If `Pname` = OFF, search only the program and current working directories. If `Pname` = STAT, list the current middle directory and show the ANSYS_MACROLIB setting.

## Notes

Specifies the pathname of a directory for file searches when reading unknown-command macro files.

The search for the files is typically from the program directory, then from the user home directory, and then from the current working directory. The command allows the middle directory searched to be other than the user home directory.

This command is valid only at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSEARCH.html
