---
apdl: "/RMDIR"
method: rmdir
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.rmdir
generated: 2026-08-22
tags: [mapdl-command]
---

# /RMDIR

PyMAPDL: `mapdl.rmdir(dir_='', **kwargs)`

Removes (deletes) a directory.

## Parameters

**dir_**: The directory to remove. If no path is provided, it will be assumed to be in the current working directory. All files in the directory are also removed.

## Notes

### Argument descriptions

- `Dir` - The directory to remove. If no path is provided, it will be assumed to be in the current working directory. All files in the directory are also removed.

Removes a directory on the computer on which Mechanical APDL is currently running. No warning or prompt is given, so use with extreme caution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RMDIR.html
