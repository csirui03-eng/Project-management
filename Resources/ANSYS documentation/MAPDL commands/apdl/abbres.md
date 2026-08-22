---
apdl: "ABBRES"
method: abbres
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.abbreviations.Abbreviations.abbres
generated: 2026-08-22
tags: [mapdl-command]
---

# ABBRES

PyMAPDL: `mapdl.abbres(lab='', fname='', ext='', **kwargs)`

Reads abbreviations from a coded file.

## Parameters

**lab**

Label that specifies the read operation:

- `NEW` - Replace current abbreviation set with these abbreviations (default).
- `CHANGE` - Extend current abbreviation set with these abbreviations, replacing any of the same name that already exist.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to ABBR if `Fname` is blank.

## Notes

### Argument descriptions

- `lab : str` - Label that specifies the read operation:
  - `NEW` - Replace current abbreviation set with these abbreviations (default).
  - `CHANGE` - Extend current abbreviation set with these abbreviations, replacing any of the same name that already exist.

\* `fname : str` - File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

\* `ext : str` - Filename extension (eight-character maximum). The extension defaults to ABBR if `Fname` is blank.

The abbreviation file may have been written with the [[abbsav|ABBSAV]] command. Do not issue **ABBRES**,NEW while inside an executing abbreviation. Doing so will cause all data for the executing abbreviation to be deleted.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ABBRES.html
