---
apdl: "FILEAUX2"
method: fileaux2
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_dump.BinaryFileDump.fileaux2
generated: 2026-08-22
tags: [mapdl-command]
---

# FILEAUX2

PyMAPDL: `mapdl.fileaux2(fname='', ident='', **kwargs)`

Specifies the binary file to be dumped.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to the current `Jobname` if `Ident` is specified.

**ident**: File name identifier. See the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for file descriptions and identifiers. If not an identifier, the program uses `Ident` as the file name extension.

## Notes

Specifies the binary file to be dumped with the [[dump|DUMP]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILEAUX2.html
