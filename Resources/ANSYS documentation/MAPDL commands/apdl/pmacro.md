---
apdl: "/PMACRO"
method: pmacro
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.macro_files.MacroFiles.pmacro
generated: 2026-08-22
tags: [mapdl-command]
---

# /PMACRO

PyMAPDL: `mapdl.pmacro(**kwargs)`

Specifies that macro contents be written to the session log file.

## Notes

This command forces the contents of a macro or other input file to be written to `Jobname.LOG`. It is valid only within a macro or input file, and should be placed at the top of the file. **/PMACRO** should be included in any macro or input file that calls GUI functions.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PMACRO.html
