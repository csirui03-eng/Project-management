---
apdl: "LGWRITE"
method: lgwrite
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.lgwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# LGWRITE

PyMAPDL: `mapdl.lgwrite(fname='', ext='', kedit='', **kwargs)`

Writes the database command log to a file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to LGW if `Fname` and `Ext` are blank.

**kedit**

Flag to suppress nonessential commands:

- `NONE` - Do not suppress any commands (default).
- `COMMENT` - Write nonessential commands as comments (starting with !).
- `REMOVE` - Do not write nonessential commands or comments.

## Notes

Writes the database command log to a named file. The database command log contains all commands that were used to create the current database. These commands are recorded in the database as they are issued, and saved in the database file ( `File.DB` ) whenever the database is saved. The **LGWRITE** command extracts these commands from the database and writes them to a file. Nonessential commands (for listing, graphics displays, help, etc.) can be excluded from the file by using the `Kedit` field. The file resulting from **LGWRITE** can be used as command input to the program. This command is most useful if the session log file ( `File.LOG` ), which is normally saved during an interactive session, has been lost or corrupted.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LGWRITE.html
