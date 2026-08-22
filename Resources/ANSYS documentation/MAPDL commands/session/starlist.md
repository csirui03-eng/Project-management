---
apdl: "*LIST"
method: starlist
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.starlist
generated: 2026-08-22
tags: [mapdl-command]
---

# *LIST

PyMAPDL: `mapdl.starlist(fname='', ext='', **kwargs)`

Displays the contents of an external, coded file.

## Parameters

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name.

**ext**: Filename extension (eight-character maximum).

## Notes

Displays the contents of an external, coded file. The file to be listed cannot be in use (open) at the time (except for the error file, `Jobname.err` None, which may be displayed with **\*LIST**,ERR).

Use caution when you are listing active Mechanical APDL files via the List\> Files\> Other and File\> List\> Other menu paths. File I/O buffer and system configurations can result in incomplete listings unless the files are closed.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LIST_st.html
