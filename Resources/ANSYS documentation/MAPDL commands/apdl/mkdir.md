---
apdl: "/MKDIR"
method: mkdir
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.mkdir
generated: 2026-08-22
tags: [mapdl-command]
---

# /MKDIR

PyMAPDL: `mapdl.mkdir(dir_='', **kwargs)`

Creates a directory.

## Parameters

**dir_**: The directory to create (248 characters maximum on Linux; 233 on Windows). If no path is provided, it will be created in the current working directory. Must be a valid name (and path) for the system you are working on.

## Notes

### Argument descriptions

- `Dir` - The directory to create (248 characters maximum on Linux; 233 on Windows). If no path is provided, it will be created in the current working directory. Must be a valid name (and path) for the system you are working on.

Creates a directory on the computer Mechanical APDL is currently running on.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MKDIR.html
