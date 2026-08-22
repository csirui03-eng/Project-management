---
apdl: "/FDELE"
method: slashfdele
group: session
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.session.files.Files.slashfdele
generated: 2026-08-22
tags: [mapdl-command]
---

# /FDELE

PyMAPDL: `mapdl.slashfdele(ident='', stat='', **kwargs)`

Deletes a binary file after it is used.

## Parameters

**ident**: Mechanical APDL file name identifier. Valid identifiers are: EMAT, ESAV, FULL, SUB, MODE, DSUB, USUB, OSAV, and SELD. See the [Basic Analysis Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS19.html) for file descriptions.

**stat**

Keep or delete key:

- `KEEP` - Keep this file.
- `DELE` - Delete (or do not write, if not necessary) this file.

## Notes

Deletes as soon as possible (or prevents writing) a binary file created by Mechanical APDL to save space.

> [!WARNING]
> Deleting files that are necessary for the next substep, load step, or analysis will prevent continuation of the run.

This command is valid only at the Begin level.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FDELE_sl.html
