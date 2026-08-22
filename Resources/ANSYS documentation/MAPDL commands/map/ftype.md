---
apdl: "FTYPE"
method: ftype
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.ftype
generated: 2026-08-22
tags: [mapdl-command]
---

# FTYPE

PyMAPDL: `mapdl.ftype(filetype='', prestype='', **kwargs)`

Specifies the file type and pressure type for the subsequent import of source points and pressures.

## Parameters

**filetype**

Type of file from which the pressure data will be retrieved (no default):

- `CFXTBR` - File from a CFX Transient Blade Row (TBR) analysis export.
- `CFDPOST` - File from a CFD-Post BC Profile export.
- `FORMATTED` - Formatted file.
- `CSV` - Comma-Separated Values file.

**prestype**

Type of pressure data contained in the file:

- `0` - Only real-valued pressures are on the file.
- `1` - Real-valued and imaginary-valued pressures are on the file (default).

## Notes

CFX Transient Blade Row files ( `FileType` = CFXTBR) are obtained from the **Export Results** Tab in CFX-Pre, with **\[Export Surface Name\]: Option** set to Harmonic Forced Response.

CFD-Post files ( `FileType` = CFDPOST) are obtained from the **Export** action in CFD-Post with **Type** set to BC Profile.

Formatted files ( `FileType` = FORMATTED) contain the coordinates and pressure data in fixed- format columns in the order x, y, z, pressure. You may have other columns of data in the file which can be skipped over in the `Format` specifier on the [[read|READ]] command, but the data must be in that order.

Comma-separated values files ( `FileType` = CSV) contain the coordinates and pressure data in comma-separated fields. The data can be in any order, and other fields of data may also be present.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FTYPE.html
