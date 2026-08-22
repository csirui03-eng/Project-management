---
apdl: "READ"
method: read
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.read
generated: 2026-08-22
tags: [mapdl-command]
---

# READ

PyMAPDL: `mapdl.read(fname='', nskip='', format_='', xfield='', yfield='', zfield='', prfield='', pifield='', **kwargs)`

Reads coordinate and pressure data from a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**nskip**: Number of lines at the beginning of the file that will be skipped while it is read. Default = 0. `NSKIP` is ignored for `FileType` = CFXTBR or CFDPOST on the [[ftype|FTYPE]] command.

**format_**: For `FileType` = FORMATTED on the [[ftype|FTYPE]] command, `Format` is the read format in the FORTRAN FORMAT convention enclosed in parentheses; for example: (3e10.0,10x,e10.0,70x,e10.0)

**xfield**, **yfield**, **zfield**, **prfield**, **pifield**: For `FileType` = CSV on the [[ftype|FTYPE]] command, these are field numbers locating the coordinates and real and imaginary (if present) pressures. The field value may not exceed 20.

## Notes

Reads coordinate and pressure data from the specified file. The file type must have been previously specified on the [[ftype|FTYPE]] command.

Upon reading the file, nodes are created for the source points. For `FileType` = CFXTBR or CFDPOST on the [[ftype|FTYPE]] command, if face data is available, `SURF154` elements are also created. A nodal component named SOURCENODES and an element component named SOURCEELEMS are created automatically.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_READ.html
