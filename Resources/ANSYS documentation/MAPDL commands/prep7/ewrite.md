---
apdl: "EWRITE"
method: ewrite
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.elements.Elements.ewrite
generated: 2026-08-22
tags: [mapdl-command]
---

# EWRITE

PyMAPDL: `mapdl.ewrite(fname='', ext='', kappnd='', format_='', **kwargs)`

Writes elements to a file.

## Parameters

**fname**

File name and directory path (up to 248 characters, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to ELEM if `Fname` is blank.

**kappnd**

Append key:

- `0` - Rewind file before the write operation.
- `1` - Append data to the end of the existing file.

**format_**

Format key:

- `SHORT` - I6 format (default).
- `LONG` - I8 format. Switches automatically to I10 if entity IDs are large.

## Notes

Writes the selected elements to a file. The write operation is unnecessary in a standard Mechanical APDL run but is provided as convenience to users wanting a coded element file.

If issuing **EWRITE** from Mechanical APDL to be used in Mechanical APDL, issue [[nwrite|NWRITE]] to store nodal information for later use.

Only elements having all of their nodes defined (and selected) are written. Data are written in a coded format. The data description of each record is: I, J, K, L, M, N, O, P, MAT, TYPE, REAL, SECNUM, ESYS, IEL, where MAT, TYPE, REAL, and ESYS are attribute numbers, SECNUM is the beam section number, and IEL is the element number.

The format is (14I6) if `Format` = SHORT, and (14I8 or 14I10) if `Format` = LONG.

One element description per record is written for elements having \<= 8 nodes. For elements having \> 8 nodes, nodes 9 and above are written on a second record using the same format.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EWRITE.html
