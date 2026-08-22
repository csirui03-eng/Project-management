---
apdl: "/STITLE"
method: stitle
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.set_up.SetUp.stitle
generated: 2026-08-22
tags: [mapdl-command]
---

# /STITLE

PyMAPDL: `mapdl.stitle(nline='', title='', **kwargs)`

Defines subtitles.

## Parameters

**nline**: Subtitle line number (1 to 4). Defaults to 1.

**title**: Input up to 70 alphanumeric characters. Parameter substitution may be forced within the title by enclosing the parameter name or parametric expression within percent (%) signs. If `Title` is blank, this subtitle is deleted.

## Notes

Up to four subtitles are displayed in the output along with the main title ( [[title|/TITLE]] ).

Subtitles do not appear in GUI windows or in plot displays.

The first subtitle is also written to various Mechanical APDL files along with the main title.

Previous subtitles can be overwritten or deleted.

Issue [[slashstatus|/STATUS]] to display titles.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_STITLE.html
