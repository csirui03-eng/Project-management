---
apdl: "CMWRITE"
method: cmwrite
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# CMWRITE

PyMAPDL: `mapdl.cmwrite(fname='', ext='', fmat='', **kwargs)`

Writes node and element components and assemblies to a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to Jobname.

**ext**: Filename extension (eight-character maximum). The extension defaults to CM if `Fname` is blank.

**fmat**

Format of the output file (defaults to BLOCKED).

- `BLOCKED` - Blocked format. This format allows faster reading of the file.
- `UNBLOCKED` - Unblocked format.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMWRITE.html
