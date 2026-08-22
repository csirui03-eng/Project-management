---
apdl: "WRITEMAP"
method: writemap
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.writemap
generated: 2026-08-22
tags: [mapdl-command]
---

# WRITEMAP

PyMAPDL: `mapdl.writemap(fname='', **kwargs)`

Writes interpolated pressure data to a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

## Notes

Writes the interpolated pressure data to the specified file. The data is written as [[sfe|SFE]] commands applied to the `SURF154` elements that are on the target surface. You may read this data for inclusion in an analysis by using [[input|/INPUT]], `Fname`.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WRITEMAP.html
