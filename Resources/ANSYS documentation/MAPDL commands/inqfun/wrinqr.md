---
apdl: "WRINQR"
method: wrinqr
group: inqfun
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.inq_func.inq_function.wrinqr
generated: 2026-08-22
tags: [mapdl-command]
---

# WRINQR

PyMAPDL: `mapdl.wrinqr(key, pname='__tmpvar__', **kwargs)`

Obtain information about output.

> [!WARNING]
> **DISCLAIMER**: This function is un-documented in the official ANSYS Command Reference Guide. Hence its support is limited and it use is not encouraged. **Please use it with caution.**

> [!WARNING]
> Caution: the following variables are "saved/resumed". key=`WR_COLINTER` thru `WR_SUPCOLMAX` in "wrinqr/wrinfo".

## Parameters

**key**

Key.

- 1 - kprint (WR_PRINT) Print flag.
  - 0 - no output
  - 1 - print

- 2 - outfil (WR_OUTPUT) Current output unit number(iott).

- 4 - frstot (WR_MASTEROUT) Master output file.

- 5 - intcol (WR_COLINTER) Interactive columns per page.

- 6 - batcol (WR_COLBATCH) Batch columns per page.

- 7 - intlin (WR_LINEINTER) Interactive lines per page.

- 8 - batlin (WR_LINEBATCH) Batch lines per page.

- 9 - CommaSep (WR_COMMASEP) 1 for comma separated output.

- 11 - chrper (WR_CHARITEM) Characters per output item.

- 12 - chrdec (WR_CHARDECIMAL) Characters past decimal.

- 13 - chrint (WR_CHARINTEGER) Characters in leading integer.

- 14 - chrtyp (WR_CHARTYPE)
  - 1 - using E format in output.
  - 2 - using F format in output.
  - 3 - using G format in output.

- 15 - (WR_TEMPLINEBATCH) Undocumented (50 default).

- 16 - keyhed (WR_SUPTITLE) Tlabel suppress key.

- 17 - keytit (WR_SUPSUBTITLE) Subtitle suppress key.

- 18 - keyid (WR_SUPLSITER) Ls,iter id suppress key.

- 19 - keynot (WR_NOTELINE) Note line suppress key.

- 20 - keylab (WR_SUPCOLHEADER)  
  column header suppress key.

- 21 - keysum (WR_SUPCOLMAX) Column maximum suppress key.

- 22 - ListOpt (WR_LISTOPT) ListOpt from /output command.

## Returns

`int or str`: The value corresponding to key.
