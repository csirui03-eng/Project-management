---
apdl: "EREAD"
method: eread
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.eread
generated: 2026-08-22
tags: [mapdl-command]
---

# EREAD

PyMAPDL: `mapdl.eread(fname='', ext='', **kwargs)`

Reads elements from a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to ELEM if `Fname` is blank.

## Notes

This read operation is not necessary in a standard anlaysis run but is provided as a convenience for those wanting to read a coded element file, such as from another mesh generator or from a CAD/CAM program.

Data should be formatted as generated via [[ewrite|EWRITE]].

If issuing **EREAD** to acquire element information generated from [[ewrite|EWRITE]], you must also issue [[nread|NREAD]] before the **EREAD** command. The element types ( [[et|ET]] ) must be defined before the file is read so that the file may be read properly. Only elements that are specified via [[errang|ERRANG]] are read from the file. Also, only elements that are fully attached to the nodes specified via [[nrrang|NRRANG]] are read from the file.

Elements are assigned numbers consecutively as read from the file, beginning with the current highest database element number plus one. The file is rewound before and after reading. Reading continues until the end of the file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EREAD.html
