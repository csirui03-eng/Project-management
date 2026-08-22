---
apdl: "*MWRITE"
method: mwrite
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.mwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# *MWRITE

PyMAPDL: `mapdl.mwrite(parr='', fname='', ext='', label='', n1='', n2='', n3='', **kwargs)`

Writes a matrix to a file in a formatted sequence.

> [!WARNING]
> This command must be run using `non_interactive <ansys.mapdl.core.Mapdl.non_interactive>`. Please visit [Unsupported Interactive Commands](https://mapdl.docs.pyansys.com/version/stable/user_guide/mapdl.html#unsupported-interactive-commands) for further information.

## Parameters

**parr**: The name of the array parameter. See [[starset|*SET]] for name restrictions.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. If the file name fields are left blank, the default file is the current output file.

**ext**: Filename extension (eight-character maximum).

**label**: Can use a value of IJK, IKJ, JIK, JKI, KIJ, KJI, or blank (JIK).

**n1**, **n2**, **n3**: Write as ((( `ParR` (i,j,k), k = 1,n1), i = 1, n2), j = 1, n3) for `Label` = KIJ. `n1,` `n2,` and `n3` default to the corresponding dimensions of the array parameter ParR.

## Notes

Writes a matrix or vector to a specified file in a formatted sequence. You can also use the [[vwrite|*VWRITE]] command to write data to a specified file. Both commands contain format descriptors on the line immediately following the command. The format descriptors can be in either FORTRAN or C format.

FORTRAN format descriptors are enclosed in parentheses. They must immediately follow the **\*MWRITE** command on a separate line of the same input file. The word FORMAT should not be included. The format must specify the number of fields to be written per line, the field width, the placement of the decimal point, etc. There should be one field descriptor for each data item written. The write operation uses the available system FORTRAN FORMAT conventions (see your system FORTRAN manual). Any standard FORTRAN real format (such as (4F6.0), (E10.3,2X,D8.2), etc.) and character format (A) may be used. Integer (I) and list-directed (2) descriptors may not be used. Text may be included in the format as a quoted string. The FORTRAN descriptor must be enclosed in parentheses and the format must not exceed 80 characters (including parentheses).

The "C" format descriptors are used if the first character of the format descriptor line is not a left parenthesis. "C" format descriptors may be up to 80 characters long, consisting of text strings and predefined "data descriptors" between the strings where numeric or alphanumeric character data are to be inserted. The normal descriptors are %I for integer data, %G for double precision data, %C for alphanumeric character data, and %/ for a line break. There must be one data descriptor for each specified value in the order of the specified values. The enhanced formats described in [[msg|*MSG]] can also be used.

The starting array element number must be defined. Looping continues in the directions indicated by the Label argument. The number of loops and loop skipping may also be controlled via [[vlen|*VLEN]] and [[vmask|*VMASK]], which work in the `n2` direction (by row on the output file), and by [[vcol|*VCOL]], which works in the `n1` direction (by column in the output file). The vector specifications [[vabs|*VABS]] and [[vfact|*VFACT]] apply to this command, while [[vcum|*VCUM]] does not apply to this command. See [[voper|*VOPER]] for details. If you are in the GUI, the **\*MWRITE** command must be contained in an externally prepared file and read into Mechanical APDL (that is, [[use|*USE]], [[input|/INPUT]], etc.).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MWRITE_st.html
