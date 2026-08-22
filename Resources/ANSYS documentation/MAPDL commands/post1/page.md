---
apdl: "/PAGE"
method: page
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.listing.Listing.page
generated: 2026-08-22
tags: [mapdl-command]
---

# /PAGE

PyMAPDL: `mapdl.page(iline='', ichar='', bline='', bchar='', comma='', **kwargs)`

Defines the printout and screen page size.

**Command default:**

As defined by the items above.

## Parameters

**iline**: Number of lines (11 minimum) per "page" or screen. Defaults to 24. Applies to interactive non- GUI to the screen output only.

**ichar**: Number of characters (41 to 132) per line before wraparound. Defaults to 80. Applies to interactive non-GUI to the screen output only.

**bline**: Number of lines (11 minimum) per page. Defaults to 56. Applies to batch mode ( `/BATCH` ), diverted ( [[output|/OUTPUT]] ), or interactive GUI ( [[menu|/MENU]] ) output. If negative, no page headers are output.

**bchar**: Number of characters (41 to 240 (system dependent)) per line before wraparound. Defaults to 140. Applies to batch mode ( `/BATCH` ), diverted ( [[output|/OUTPUT]] ), or interactive GUI ( [[menu|/MENU]] ) output.

**comma**: Input 1 to specify comma-separated output for node ( [[nlist|NLIST]] ) and element ( [[elist|ELIST]] ) output.

## Notes

Defines the printout page size for batch runs and the screen page size for interactive runs. Applies to the POST1 [[prnsol|PRNSOL]], [[presol|PRESOL]], [[pretab|PRETAB]], [[prrsol|PRRSOL]], and [[prpath|PRPATH]] commands. See the [[header|/HEADER]] command for additional controls (page ejects, headers, etc.) that affect the amount of printout. A blank (or out-of-range) value retains the previous setting. Issue **/PAGE** ,STAT to display the current settings. Issue **/PAGE**,DEFA to reset the default specifications.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PAGE.html
