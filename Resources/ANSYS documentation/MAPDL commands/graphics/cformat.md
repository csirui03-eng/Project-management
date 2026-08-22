---
apdl: "/CFORMAT"
method: cformat
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.cformat
generated: 2026-08-22
tags: [mapdl-command]
---

# /CFORMAT

PyMAPDL: `mapdl.cformat(nfirst='', nlast='', **kwargs)`

Controls the graphical display of alphanumeric character strings for parameters, components, assemblies, and tables.

## Parameters

**nfirst**: Display the first `n` characters of the parameter, component, assembly, or table name, up to 32. Defaults to 32.

**nlast**: Display the last `n` characters of the parameter, component, assembly, or table name, up to 32. Defaults to 0.

## Notes

Use this command to control the length of the character string that is shown in the graphics window for a parameter, component, assembly, or table name.

The total number of characters ( `NFIRST` + `NLAST` +3) cannot exceed 32.

If `NFIRST` is greater than zero and `NLAST` = 0, only the `NFIRST` characters are displayed, followed by an ellipsis.

If `NFIRST` = 0 and `NLAST` is greater than zero, only the `NLAST` characters are displayed, preceded by an ellipsis (...).

If both `NFIRST` and `NLAST` are greater than zero, the name will be shown as `NFIRST`, followed by an ellipsis (...), followed by `NLAST`, up to a maximum of 32 characters.

For example, if `NFIRST` = 6 and `NLAST` = 3, and the character string is LENGTHOFSIDEONE, then it will appear in the graphics window as LENGTH...ONE.

If the actual length of the character string is less than the specified combination of `NFIRST` + `NLAST` +3, then the actual string will be used.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CFORMAT_sl.html
