---
apdl: "NWRITE"
method: nwrite
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# NWRITE

PyMAPDL: `mapdl.nwrite(fname='', ext='', kappnd='', **kwargs)`

Writes nodes to a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to NODE if `Fname` is blank.

**kappnd**

Append key:

- `0` - Rewind file before the write operation.
- `1` - Append data to the end of the existing file.

## Notes

Writes selected nodes ( [[nsel|NSEL]] \]) to a file. The write operation is not necessary in a standard Mechanical APDL run but is provided as a convenience to those who want coded node file.

Data are written in a coded format. The format used is (I9, 6G21.13E3) to write out `NODE`, `X`, `Y`, `Z`, `THXY`, `THYZ`, `THZX`. If the last number is zero ( `THZX` = 0), or the last set of numbers are zero, they are not written but are left blank. Therefore, use a formatted read to process this file.

Coordinate values are in the global Cartesian system.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NWRITE.html
