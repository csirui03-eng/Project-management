---
apdl: "SUSAVE"
method: susave
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.susave
generated: 2026-08-22
tags: [mapdl-command]
---

# SUSAVE

PyMAPDL: `mapdl.susave(lab='', fname='', fext='', fdir='', **kwargs)`

Saves surface definitions to a file.

## Parameters

**lab**

Eight-character surface name.

If `Lab` = ALL (default), then all surfaces are saved to the file.

If `Lab` = S, only currently selected surfaces are saved to the file.

**fname**: File name and directory path (248 character maximum, including directory). If you do not specify a directory path, the default is your working directory and you can use all 248 characters for the file name. The file name defaults to the jobname.

**fext**: File name extension (eight-character maximum). The extension defaults to "surf".

**fdir**: Optional path specification.

## Notes

The **SUSAVE** command saves surface definitions (geometry information)-and any result items mapped onto the surfaces-to a file.

Issuing the **SUSAVE** command has no effect on the database. The database remains unchanged.

Subsequent executions of the **SUSAVE** command overwrite previous data in the file.

To read the contents of the file created via the **SUSAVE** command, issue the [[suresu|SURESU]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUSAVE.html
