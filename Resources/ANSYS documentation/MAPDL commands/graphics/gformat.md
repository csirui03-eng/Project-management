---
apdl: "/GFORMAT"
method: gformat
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.gformat
generated: 2026-08-22
tags: [mapdl-command]
---

# /GFORMAT

PyMAPDL: `mapdl.gformat(ftype='', nwidth='', dsignf='', **kwargs)`

Specifies the format for the graphical display of numbers.

## Parameters

**ftype**

FORTRAN format types (G is the default if this field is left blank.)

- `G` - G `xx`. `yy`. `xx` and `yy` are described below.
- `F` - F `xx`. `yy`
- `E` - E `xx`. `yy`

**nwidth**: Total width (12 maximum) of the field (the `xx` in `Ftype` ). Defaults to 12.

**dsignf**: Number of digits after the decimal point ( `yy` in F or E format) or number of significant digits in G format. Range is 1 to `xx` -6 for `Ftype` = G or E; and 0 to `xx` -3 for `Ftype` = F. The default is a function of `Ftype` and `NWIDTH`.

## Notes

Enables you to control the format of the graphical display of floating point numbers.

To display the current settings, issue **/GFORMAT**,STAT..

To allow Mechanical APDL to select the format for the graphical display of floating numbers, issue **/GFORMAT**,DEFA.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GFORMAT.html
