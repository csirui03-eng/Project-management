---
apdl: "*VREAD"
method: vread
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.parameter_definition.ParameterDefinition.vread
generated: 2026-08-22
tags: [mapdl-command]
---

# *VREAD

PyMAPDL: `mapdl.vread(parr='', fname='', ext='', label='', n1='', n2='', n3='', nskip='', **kwargs)`

Reads data and produces an array parameter vector or matrix.

## Parameters

**parr**: The name of the resulting array parameter vector. See [[starset|*SET]] for name restrictions. The parameter must exist as a dimensioned array ( [[dim|*DIM]] ). String arrays are limited to a maximum of 8 characters.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. If the `Fname` field is left blank, reading continues from the current input device, such as the terminal.

**ext**: Filename extension (eight-character maximum).

**label**: Can take a value of IJK, IKJ, JIK, JKI, KIJ, KJI, or blank (IJK).

**n1**, **n2**, **n3**: Read as ((( `ParR` (i,j,k), k = 1,n1), i = 1, n2), j = 1, n3) for `Label` = KIJ. `n2` and `n3` default to 1.

**nskip**: Number of lines at the beginning of the file being read that will be skipped during the reading. Default = 0.

## Notes

### Argument descriptions

- `parr : str` - The name of the resulting array parameter vector. See [[starset|*SET]] for name restrictions. The parameter must exist as a dimensioned array ( [[dim|*DIM]] ). String arrays are limited to a maximum of 8 characters.

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. If the `Fname` field is left blank, reading continues from the current input device, such as the terminal.

- `ext : str` - Filename extension (eight-character maximum).
- `label : str` - Can take a value of IJK, IKJ, JIK, JKI, KIJ, KJI, or blank (IJK).
- `n1, n2, n3 : str` - Read as ((( `ParR` (i,j,k), k = 1,n1), i = 1, n2), j = 1, n3) for `Label` = KIJ. `n2` and `n3` default to 1.
- `nskip : str` - Number of lines at the beginning of the file being read that will be skipped during the reading. Default = 0.

Reads data from a file and fills in an array parameter vector or matrix. Data are read from a formatted file or, if the menu is off ( [[menu|/MENU]],OFF) and `Fname` is blank, from the next input lines. The format of the data to be read must be input immediately following the **\*VREAD** command. The format specifies the number of fields to be read per record, the field width, and the placement of the decimal point (if none specified in the value). The read operation follows the available FORTRAN FORMAT conventions of the system (see your system FORTRAN manual). Any standard FORTRAN real format (such as (4F6.0), (E10.3,2X,D8.2), etc.) or alphanumeric format (A) may be used. Alphanumeric strings are limited to a maximum of 8 characters for any field (A8). For storage of string arrays greater than 8 characters, the \*SREAD command can be used. Integer (I) and list- directed (2) descriptors may not be used. The parentheses must be included in the format and the format must not exceed 80 characters (including parentheses). The input line length is limited to 128 characters.

A starting array element number must be defined for the result array parameter vector (numeric or character). For example, entering these two lines:

``` apdl
*VREAD,A(1),ARRAYVAL
(2F6.0)
```

will read two values from each line of file ARRAYVAL and assign the values to A(1), A(2), A(3), etc. Reading continues until successive row elements ( [[vlen|*VLEN]], [[vmask|*VMASK]], [[dim|*DIM]] ) are filled.

For an array parameter matrix, a starting array element row and column number must be defined. For example, entering these two lines:

``` apdl
*VREAD,A(1,1),ARRAYVAL,,,IJK,10,2
(2F6.0)
```

will read two values from each line of file ARRAYVAL and assign the values to A(1,1), A(2,1), A(3,1), etc. Reading continues until `n1` (10) successive row elements are filled. Once the maximum row number is reached, subsequent data will be read into the next column (for example, A(1,2), A(2,2), A(3,2), etc.)

For numerical parameters, absolute values and scale factors may be applied to the result parameter ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). See the [[voper|*VOPER]] command for details. If you are in the GUI the **\*VREAD** command must be contained in an externally prepared file read into Mechanical APDL (that is, [[use|*USE]], [[input|/INPUT]], etc.).

This command is not applicable to 4- or 5-D arrays.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VREAD.html
