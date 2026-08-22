---
apdl: "/FORMAT"
method: format
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.listing.Listing.format
generated: 2026-08-22
tags: [mapdl-command]
---

# /FORMAT

PyMAPDL: `mapdl.format(ndigit='', ftype='', nwidth='', dsignf='', line='', char_='', exptype='', **kwargs)`

Specifies format controls for tables.

## Parameters

**ndigit**: Number of digits (3 to 32) in first table column (usually the node or element number). Initially defaults to 7.

**ftype**

FORTRAN format type:

- `G` - G `xx.yy` (default)
- `F` - F `xx.yy`
- `E` - E `xx.yy`

where `xx` and `yy` are described below.

**nwidth**: Total width (9 to 32) of the field ( `xx` in `Ftype` ). Default = 13.

**dsignf**: Number of digits after the decimal point ( `yy` in F or E format) or number of significant digits in G format. Range is 2 to `xx` -7 for `Ftype` = G or E; and 0 to `xx` -4 for `Ftype` = F. Default = 5.

**line**: Number of lines (11 minimum) per page. Default = `ILINE` or `BLINE` ( [[page|/PAGE]] ).

**char_**: Number of characters (41 to 240, system-dependent) per line before wraparound. Default = `ICHAR` or `BCHAR` ( [[page|/PAGE]] ).

**exptype**

Number of digits for the exponent ( `Ftype` = G):

- `3` - Three digits (default).
- `2` - Two digits.

## Notes

Specifies various format controls for tables printed with the POST1 [[prnsol|PRNSOL]], [[presol|PRESOL]], [[pretab|PRETAB]], [[prrsol|PRRSOL]], [[prpath|PRPATH]], and [[cyccalc|CYCCALC]] commands. A blank (or out-of-range) field on the command retains the current setting. Issue **/FORMAT**,STAT to display the current settings. Issue **/FORMAT**,DEFA to reestablish the initial default specifications.

For the POST26 [[prvar|PRVAR]] command, the `Ftype`, `NWIDTH`, and `DSIGNF` fields control the time output format.

When viewing integer output quantities, the floating point format may lead to incorrect output values for large integers. You should verify large integer output values via the [[get|*GET]] command whenever possible.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FORMAT.html
