---
apdl: "PARESU"
method: paresu
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.paresu
generated: 2026-08-22
tags: [mapdl-command]
---

# PARESU

PyMAPDL: `mapdl.paresu(lab='', fname='', ext='', **kwargs)`

Restores previously saved paths from a file.

## Parameters

**lab**

Read operation:

- `ALL` - Read all paths from the selected file (default).

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to PATH if `Fname` is blank.

## Notes

This command removes all paths from virtual memory and then reads path data from a file written with the [[pasave|PASAVE]] command. All paths on the file will be restored. All paths currently in memory will be deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PARESU.html
