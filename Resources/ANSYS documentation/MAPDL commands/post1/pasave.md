---
apdl: "PASAVE"
method: pasave
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.pasave
generated: 2026-08-22
tags: [mapdl-command]
---

# PASAVE

PyMAPDL: `mapdl.pasave(lab='', fname='', ext='', **kwargs)`

Saves selected paths to an external file.

## Parameters

**lab**

Write operation:

- `S` - Saves only selected paths.
- `ALL` - Saves all paths (default).
- `Pname` - Saves the named path (from the [[psel|PSEL]] command).

**fname**

File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext**

Filename extension (eight-character maximum).

The extension defaults to PATH if `Fname` is blank.

## Notes

Saves the paths selected with the [[psel|PSEL]] command to an external file (default `Jobname.path` ).

Previous paths on this file, if any, are overwritten. The path file can be read via [[paresu|PARESU]].

This command is valid in POST1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PASAVE.html
