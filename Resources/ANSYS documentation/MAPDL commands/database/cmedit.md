---
apdl: "CMEDIT"
method: cmedit
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.components.Components.cmedit
generated: 2026-08-22
tags: [mapdl-command]
---

# CMEDIT

PyMAPDL: `mapdl.cmedit(aname='', oper='', cnam1='', cnam2='', cnam3='', cnam4='', cnam5='', cnam6='', cnam7='', **kwargs)`

Edits an existing assembly.

## Parameters

**aname**: Name of the assembly to be edited.

**oper**

Operation label:

- `ADD` - To add more components. The level of any assembly to be added must be lower than that of the assembly `Aname` (see [[cmgrp|CMGRP]] command).
- `DELE` - To remove components.

**cnam1**, **cnam2**, **cnam3**, **cnam4**, **cnam5**, **cnam6**, **cnam7**: Names of components and assemblies to be added to or deleted from the assembly.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CMEDIT.html
