---
apdl: "TVAR"
method: tvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.controls.Controls.tvar
generated: 2026-08-22
tags: [mapdl-command]
---

# TVAR

PyMAPDL: `mapdl.tvar(key='', **kwargs)`

Changes time to the cumulative iteration number.

## Parameters

**key**

Time key:

- `0` - Time is used for the variable `TIME`.
- `1` - NCUMIT is used for the variable `TIME`.

## Notes

Changes the meaning of the time variable to the cumulative iteration number (NCUMIT) variable. Data can be read from the file, printed, and displayed as a function of NCUMIT rather than time. All POST26 descriptions applying to TIME then apply to NCUMIT.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TVAR.html
