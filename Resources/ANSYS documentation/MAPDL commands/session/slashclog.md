---
apdl: "/CLOG"
method: slashclog
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.slashclog
generated: 2026-08-22
tags: [mapdl-command]
---

# /CLOG

PyMAPDL: `mapdl.slashclog(fname='', ext='', **kwargs)`

Copies the session log file to a named file.

## Parameters

**fname**: File name and directory path to which the log file is to be copied (248 characters maximum, including directory). If you do not specify a directory path, it will default to your working directory and you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

## Notes

This command is valid in any processor, but only during an interactive run.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLOG_sl.html
