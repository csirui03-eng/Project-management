---
apdl: "IGESIN"
method: igesin
group: aux15
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux15.iges.Iges.igesin
generated: 2026-08-22
tags: [mapdl-command]
---

# IGESIN

PyMAPDL: `mapdl.igesin(fname='', ext='', **kwargs)`

Transfers IGES data from a file into Mechanical APDL.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to CAD if `Fname` is blank.

## Notes

Reads a file containing IGES data and transfers it into the Mechanical APDL database. The file transferred is the IGES Version 5.1, ASCII format file. IGES (Initial Graphics Exchange Specification) is a neutral format developed by the U.S. Dept. of Commerce, National Institute of Standards and Technology. No output transfer file is written because the transferred data is read directly into the Mechanical APDL database.

You can import multiple files into a single database, but you must use the same import option (set with the [[ioptn|IOPTN]] command) for each file.

The [[ioptn|IOPTN]] command sets the parameters for reading the file. Files read via the SMOOTH method (the only available method) use the standard database.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IGESIN.html
