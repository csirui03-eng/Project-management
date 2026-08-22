---
apdl: "/SECLIB"
method: seclib
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.cross_sections.CrossSections.seclib
generated: 2026-08-22
tags: [mapdl-command]
---

# /SECLIB

PyMAPDL: `mapdl.seclib(option='', path='', **kwargs)`

Sets the default section library path for the [[secread|SECREAD]] command.

## Parameters

**option**

- `READ` - Sets the read path (default).
- `STATUS` - Reports the current section library path setting to the `Jobname.LOG` file.

**path**: Defines the directory path from which to read section library files.

## Notes

When the [[secread|SECREAD]] command is issued without a directory path, the command searches for a section library in the following order:

- The user's home directory
- The current working directory
- The path specified by the **/SECLIB** command

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SECLIB.html
