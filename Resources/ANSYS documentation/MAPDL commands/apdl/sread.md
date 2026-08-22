---
apdl: "*SREAD"
method: sread
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.sread
generated: 2026-08-22
tags: [mapdl-command]
---

# *SREAD

PyMAPDL: `mapdl.sread(strarray='', fname='', ext='', nchar='', nskip='', nread='', **kwargs)`

Reads a file into a string array parameter.

## Parameters

**strarray**: Name of the string array parameter which will hold the read file. String array parameters are similar to character arrays, but each array element can be as long as 248 characters. If the string parameter does not exist, it will be created. The array will be created as: \*DIM,StrArray,STRING,nChar,nRead

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

**nchar**: Number of characters per line to read (default is length of the longest line in the file).

**nskip**: Number of lines to skip at the start of the file (default is 0).

**nread**: Number of lines to read from the file (default is the entire file).

## Notes

The **\*SREAD** command reads from a file into a string array parameter. The file must be an ASCII text file.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SREAD_st.html
