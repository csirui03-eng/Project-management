---
apdl: "DUMP"
method: dump
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_dump.BinaryFileDump.dump
generated: 2026-08-22
tags: [mapdl-command]
---

# DUMP

PyMAPDL: `mapdl.dump(nstrt='', nstop='', **kwargs)`

Dumps the contents of a binary file.

## Parameters

**nstrt**, **nstop**: Dump file from record `NSTRT` (defaults to 1) to `NSTOP` (defaults to `NSTRT` ). If `NSTRT` = HEAD, dump only record 1 of the file ( `NSTOP` and the format specification are ignored). If `NSTRT` = ALL, dump the entire file.

## Notes

Dumps the file named on the AUX2 [[fileaux2|FILEAUX2]] command according the format specified on the [[form|FORM]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DUMP.html
