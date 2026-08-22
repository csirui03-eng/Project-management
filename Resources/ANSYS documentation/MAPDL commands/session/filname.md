---
apdl: "/FILNAME"
method: filname
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.run_controls.RunControls.filname
generated: 2026-08-22
tags: [mapdl-command]
---

# /FILNAME

PyMAPDL: `mapdl.filname(fname='', key='', **kwargs)`

Changes the Jobname for the analysis.

## Parameters

**fname**: Name (32 characters maximum) to be used as the `Jobname`. Defaults to the initial `Jobname` as specified on the Mechanical APDL execution command, or to `file` if none specified.

**key**

Specify whether to use the existing log, error, lock, page, and output files ( `.LOG`, `.ERR`, `.LOCK`, `.PAGE` and `.OUT` ) or start new files.

- `0, OFF` - Continue using current log, error, lock, page, and output files.
- `1, ON` - Start new log, error, lock, page, and output files (old log and error files are closed and saved, but old lock, page, and output files are deleted). Existing log and error files are appended.

## Notes

All subsequently created files will be named with this `Jobname` if `Key` = 0. Use `Key` = 1 to start new log, error, lock, page, and output files. The previous `Jobname` is typically defined on the Mechanical APDL program execution line. (See the [Operations Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_ope/Hlp_G_OPE8.html).

This command is useful when different groups of files created throughout the run are to have different names. For example, the command may be used before each substructure pass to avoid overwriting files or having to rename each file individually.

This command is valid only at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FILNAME.html
