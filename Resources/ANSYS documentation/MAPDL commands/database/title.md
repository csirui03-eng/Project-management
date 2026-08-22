---
apdl: "/TITLE"
method: title
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.title
generated: 2026-08-22
tags: [mapdl-command]
---

# /TITLE

PyMAPDL: `mapdl.title(title='', **kwargs)`

Defines a main title.

## Parameters

**title**: Input up to 72 alphanumeric characters. Parameter substitution may be forced within the title by enclosing the parameter name or parametric expression within percent (%) signs.

## Notes

The title is carried through the printout and written on various files. The title written to a file is the title defined at that time. Special characters may be used within the title text. Subtitles may also be defined ( [[stitle|/STITLE]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TITLE.html
