---
apdl: "RMORE"
method: rmore
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.real_constants.RealConstants.rmore
generated: 2026-08-22
tags: [mapdl-command]
---

# RMORE

PyMAPDL: `mapdl.rmore(r7='', r8='', r9='', r10='', r11='', r12='', **kwargs)`

Adds real constants to a set.

## Parameters

**r7**, **r8**, **r9**, **r10**, **r11**, **r12**: Add real constants 7 to 12 (numerical values or table names) to the most recently defined set.

## Notes

Adds six more real constants to the most recently defined set. Repeat the **RMORE** command for constants 13 to 18, again for 19-24, etc.

If using table inputs ( `SURF151`, `SURF152`, `FLUID116`, `CONTA172`, `CONTA174`, `CONTA175`, and `CONTA177` only), enclose the table name in % signs (for example, `%tabname%` ).

When copying real constants to new sets, Ansys, Inc. recommends that you use the command input. If you do use the GUI, restrict the real constant copy to only the first six real constants (real constants seven and greater will be incorrect for both the master and copy set).

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RMORE.html
