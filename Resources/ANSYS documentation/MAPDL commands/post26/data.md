---
apdl: "DATA"
method: data
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.set_up.SetUp.data
generated: 2026-08-22
tags: [mapdl-command]
---

# DATA

PyMAPDL: `mapdl.data(ir='', lstrt='', lstop='', linc='', name='', kcplx='', **kwargs)`

Reads data records from a file into a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**lstrt**: Start at location `LSTRT` (defaults to 1).

**lstop**: Stop at location `LSTOP` (defaults to `LSTRT` ). Maximum location available is determined from data previously stored.

**linc**: Fill every `LINC` location between `LSTRT` and `LSTOP` (defaults to 1).

**name**: Eight character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**kcplx**

Complex number key:

- `0` - Data stored as the real part of the complex number.
- `1` - Data stored as the imaginary part of the complex number.

## Notes

This command must be followed by a format statement (on the next line) and the subsequent data records, and all must be on the same file (that may then be read with the [[input|/INPUT]] command). The format specifies the number of fields to be read per record, the field width, and the placement of the decimal point (if one is not included in the data value). The read operation follows the available FORTRAN FORMAT conventions of the system. See the system FORTRAN manual for details. Any standard FORTRAN real format (such as (4F6.0), (F2.0,2X,F12.0), etc.) may be used. Integer (I), character (A), and list-directed (2) descriptors may not be used. The parentheses must be included in the format. Up to 80 columns per record may be read. Locations may be filled within a range. Previous data in the range will be overwritten.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DATA.html
