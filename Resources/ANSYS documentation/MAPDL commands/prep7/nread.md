---
apdl: "NREAD"
method: nread
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nread
generated: 2026-08-22
tags: [mapdl-command]
---

# NREAD

PyMAPDL: `mapdl.nread(fname='', ext='', **kwargs)`

Reads nodes from a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to NODE if `Fname` is blank.

## Notes

The read operation is not necessary in a standard Mechanical APDL run but is provided as a convenience for those who want to read a coded node file (such as from another mesh generator or from a CAD/CAM program).

Data should be formatted as produced via [[nwrite|NWRITE]].

Only nodes within the node range specified via [[nrrang|NRRANG]] are read from the file. Duplicate nodes already in the database are overwritten.

The file is rewound before and after reading. Reading continues until the end of the file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NREAD.html
