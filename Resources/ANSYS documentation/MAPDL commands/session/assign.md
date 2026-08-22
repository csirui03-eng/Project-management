---
apdl: "/ASSIGN"
method: assign
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.assign
generated: 2026-08-22
tags: [mapdl-command]
---

# /ASSIGN

PyMAPDL: `mapdl.assign(ident='', fname='', ext='', lgkey='', **kwargs)`

Reassigns a file name to a Mechanical APDL file identifier.

## Parameters

**ident**: Mechanical APDL file name identifier. Valid identifiers are: CMS, EMAT, EROT, ESAV, FULL, LN07, LN09, LN11, LN20, LN21, LN22, LN25, LN31, LN32, MODE, OSAV, RDSP, RFRQ, RMG, RST, RSTP, RTH, SELD, and SSCR. See [File Management and Files](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS18_9.html)

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

**lgkey**

Key to specify local or global file name control for the specified file identifier in a distributed- memory parallel processing run. For more information on local and global files, see File Handling Conventions in the [Parallel Processing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_dan/HybParallel.html).

- `BOTH` - Reassign the file name for both the local and global files (default).
- `LOCAL` - Reassign the file name for only the local files.
- `GLOBAL` - Reassign the file name for only the global file.

## Notes

The reassignment of file names is valid only if it is done before the file is used. All file reassignments are retained (not cleared) even if the database is cleared ( [[clear|/CLEAR]] ) or the Jobname is changed ( [[filname|/FILNAME]] ). Assigned files may be overwritten. If file name arguments (`Fname`, `Ext`, `--`) are blank, the default Mechanical APDL assignment is restored. Use [[seopt|SEOPT]] for SUB files and [[seexp|SEEXP]] for DSUB files.

This command is valid only at the Begin level.

This command also checks to ensure that the path/file is valid and can be written by the user. If it is not valid, an error message will be returned. Ensure that the directory exists prior to using **/ASSIGN** command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASSIGN.html
