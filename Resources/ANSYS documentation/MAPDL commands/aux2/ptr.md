---
apdl: "PTR"
method: ptr
group: aux2
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux2.binary_file_dump.BinaryFileDump.ptr
generated: 2026-08-22
tags: [mapdl-command]
---

# PTR

PyMAPDL: `mapdl.ptr(loc='', base='', loch='', baseh='', **kwargs)`

Dumps the record of a binary file.

## Parameters

**loc**, **base**: Dump the file record starting at pointer `LOC`. `BASE` is the base pointer, and would be used if `LOC` is a relative pointer.

**loch**, **baseh**: Second 32-bit integer (if required) for defining the 64-bit pointer.

## Notes

Dumps the record of the file named on the AUX2 [[fileaux2|FILEAUX2]] command according the format specified on the [[form|FORM]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PTR.html
