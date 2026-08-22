---
apdl: "CDOPT"
method: cdopt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.cdopt
generated: 2026-08-22
tags: [mapdl-command]
---

# CDOPT

PyMAPDL: `mapdl.cdopt(option='', **kwargs)`

Specifies format to be used for archiving geometry.

## Parameters

**option**

- `IGES` - Write solid model geometry information using IGES format (default).
- `ANF` - Write solid model geometry information using Ansys Neutral File (ANF) format.
- `STAT` - Print out the current format setting.

## Notes

This command controls your solid model geometry format for [[cdwrite|CDWRITE]] operations. The ANF option affects only the COMB and SOLID options of the [[cdwrite|CDWRITE]] command. All other options remain unaffected.

This option setting is saved in the database.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CDOPT.html
