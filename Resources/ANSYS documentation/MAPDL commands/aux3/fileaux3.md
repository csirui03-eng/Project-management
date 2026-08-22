---
apdl: "FILEAUX3"
method: fileaux3
group: aux3
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux3.results_files.ResultsFiles.fileaux3
generated: 2026-08-22
tags: [mapdl-command]
---

# FILEAUX3

PyMAPDL: `mapdl.fileaux3(fname='', ext='', **kwargs)`

Specifies the results file to be edited.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to the current `Jobname` if `Ext` is specified.

**ext**: Filename extension (eight-character maximum).

## Notes

Specifies the results file to be edited.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILEAUX3.html
