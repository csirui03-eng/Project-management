---
apdl: "ABBSAV"
method: abbsav
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.abbreviations.Abbreviations.abbsav
generated: 2026-08-22
tags: [mapdl-command]
---

# ABBSAV

PyMAPDL: `mapdl.abbsav(lab='', fname='', ext='', **kwargs)`

Writes the current abbreviation set to a coded file.

## Parameters

**lab**

Label that specifies the write operation:

- `ALL` - Write all abbreviations (default).

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to ABBR if `Fname` is blank.

## Notes

### Argument descriptions

- `lab : str` - Label that specifies the write operation:
  - `ALL` - Write all abbreviations (default).

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

\* `ext : str` - Filename extension (eight-character maximum). The extension defaults to ABBR if `Fname` is blank.

Existing abbreviations on this file, if any, will be overwritten. The abbreviation file may be read with the [[abbres|ABBRES]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ABBSAV.html
